Quick Reference
===============

Command-line only options for all runners
-----------------------------------------

=================== ======================================================= ========================================================
Option              Default                                                 Switches
=================== ======================================================= ========================================================
*conf_path*         (automatic; see :py:func:`~mrjob.conf.find_mrjob.conf`) :option:`-c`, :option:`--conf-path`, :option:`--no-conf`
*extra_args*        ``[]``                                                  (see :py:meth:`~mrjob.job.MRJob.add_passthrough_option`)
*file_upload_args*  ``[]``                                                  (see :py:meth:`~mrjob.job.MRJob.add_file_option`)
*output_dir*        (automatic)                                             :option:`-o`, :option:`--output-dir`
=================== ======================================================= ========================================================

See :py:meth:`mrjob.runner.MRJobRunner.__init__` for details.

Options for all runners
-----------------------

=================== ============================== ========================================= ===========================
Option              Default                        Combined by                               Switches
=================== ============================== ========================================= ===========================
*base_tmp_dir*      :envvar:`TMPDIR` or ``'/tmp'`` :py:func:`~mrjob.conf.combine_paths`
*bootstrap_mrjob*   ``True``                       :py:func:`~mrjob.conf.combine_values`
*cleanup*           ``'IF_SUCCESSFUL'``            :py:func:`~mrjob.conf.combine_values`     :option:`--cleanup`
*cmdenv*            ``{}``                         :py:func:`~mrjob.conf.combine_envs`
*hadoop_extra_args* ``[]``                         :py:func:`~mrjob.conf.combine_lists`      :option:`--hadoop-arg`
*job_name_prefix*   (automatic)                    :py:func:`~mrjob.conf.combine_values`     :option:`--job-name-prefix`
*jobconf*           ``{}``                         :py:func:`~mrjob.conf.combine_dicts`      :option:`--jobconf`
*python_archives*   ``[]``                         :py:func:`~mrjob.conf.combine_path_lists`
*setup_cmds*        ``[]``                         :py:func:`~mrjob.conf.combine_lists`
*setup_scripts*     ``[]``                         :py:func:`~mrjob.conf.combine_path_lists`
*upload_archives*   ``[]``                         :py:func:`~mrjob.conf.combine_path_lists` :option:`--archive`
*upload_files*      ``[]``                         :py:func:`~mrjob.conf.combine_path_lists` :option:`--file`
=================== ============================== ========================================= ===========================

See :py:meth:`mrjob.runner.MRJobRunner.__init__` for details.

:py:class:`~mrjob.local.LocalMRJobRunner` takes no additional options.

Additional options for :py:class:`~mrjob.emr.EMRJobRunner`
----------------------------------------------------------

=========================== ============================== ========================================= =====================================
Option                      Default                        Combined by                               Switches
=========================== ============================== ========================================= =====================================
*aws_access_key_id*         (automatic)                    :py:func:`~mrjob.conf.combine_values`
*aws_secret_access_key*     (automatic)                    :py:func:`~mrjob.conf.combine_values`
*aws_region*                (automatic)                    :py:func:`~mrjob.conf.combine_values`
*bootstrap_cmds*            ``[]``                         :py:func:`~mrjob.conf.combine_lists`
*bootstrap_files*           ``[]``                         :py:func:`~mrjob.conf.combine_path_lists`
*bootstrap_python_packages* ``[]``                         :py:func:`~mrjob.conf.combine_path_lists`
*bootstrap_scripts*         ``[]``                         :py:func:`~mrjob.conf.combine_values`
*check_emr_status_every*    ``30``                         :py:func:`~mrjob.conf.combine_values`     :option:`--check-emr-status-every`
*ec2_instance_type*         ``'m1.small'``                 :py:func:`~mrjob.conf.combine_values`     :option:`--ec2-instance-type`
*ec2_key_pair*              ``None``                       :py:func:`~mrjob.conf.combine_values`
*ec2_key_pair_file*         ``None``                       :py:func:`~mrjob.conf.combine_paths`
*ec2_master_instance_type*  (same as *ec2_instance_type*)  :py:func:`~mrjob.conf.combine_values`     :option:`--ec2-master-instance-type`
*ec2_slave_instance_type*   (same as *ec2_instance_type*)  :py:func:`~mrjob.conf.combine_values`     :option:`--ec2-slave-instance-type`
*emr_endpoint*              (automatic)                    :py:func:`~mrjob.conf.combine_values`
*emr_job_flow_id*           ``None``                       :py:func:`~mrjob.conf.combine_values`
*num_ec2_instances*         ``1``                          :py:func:`~mrjob.conf.combine_values`     :option:`--num-ec2-instances`
*s3_endpoint*               (automatic)                    :py:func:`~mrjob.conf.combine_paths`
*s3_log_uri*                (automatic)                    :py:func:`~mrjob.conf.combine_paths`      :option:`--s3-log-uri`
*s3_scratch_uri*            (automatic)                    :py:func:`~mrjob.conf.combine_values`     :option:`--s3-scratch-uri`
*s3_sync_wait_time*         ``5.0``                        :py:func:`~mrjob.conf.combine_values`
*ssh_bin*                   ``'ssh'``                      :py:func:`~mrjob.conf.combine_paths`
*ssh_bind_ports*            ``range(40001, 40841)``        :py:func:`~mrjob.conf.combine_values`
*ssh_tunnel_to_job_tracker* ``False``                      :py:func:`~mrjob.conf.combine_values`     :option:`--ssh-tunnel-to-job-tracker`
*ssh_tunnel_is_open*        ``False``                      :py:func:`~mrjob.conf.combine_values`     :option:`--ssh-tunnel-is-open`
=========================== ============================== ========================================= =====================================

See :py:meth:`mrjob.emr.EMRJobRunner.__init__` for details.

Additional options for :py:class:`~mrjob.hadoop.HadoopJobRunner`
----------------------------------------------------------------

====================== =========================== ===================================== ================================
Option                 Default                     Combined by                           Switches
====================== =========================== ===================================== ================================
*hadoop_bin*           (automatic)                 :py:func:`~mrjob.conf.combine_paths`  :option:`--hadoop-bin`
*hadoop_home*          :envvar:HADOOP_HOME         :py:func:`~mrjob.conf.combine_values`
*hdfs_scratch_dir*     ``tmp/mrjob`` (in HDFS)     :py:func:`~mrjob.conf.combine_paths`  :option:`--hdfs-scratch-dir`
*hadoop_streaming_jar* (automatic)                 :py:func:`~mrjob.conf.combine_paths`  :option:`--hadoop-streaming-jar`
====================== =========================== ===================================== ================================

See :py:meth:`mrjob.hadoop.HadoopJobRunner.__init__` for details.
