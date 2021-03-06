if ENABLE_TESTBENCH
CLEANFILES = \
	IN_AUTO_DEBUG
# IN_AUTO_DEBUG should be deleted each time make check is run, but
# there exists no such hook. Se we at least delete it on make clean.

# TODO: reenable TESTRUNS = rt_init rscript
check_PROGRAMS = $(TESTRUNS) ourtail nettester tcpflood chkseq msleep randomgen diagtalker uxsockrcvr syslog_caller inputfilegen minitcpsrv
TESTS = $(TESTRUNS) 
#TESTS = $(TESTRUNS) cfg.sh

TESTS +=  \
	stop-localvar.sh \
	stop-msgvar.sh \
	msgvar-concurrency.sh \
	localvar-concurrency.sh \
	fac_authpriv.sh \
	fac_local0.sh \
	fac_local7.sh \
	fac_mail.sh \
	fac_news.sh \
	fac_ftp.sh \
	fac_ntp.sh \
	fac_uucp.sh \
	fac_invld1.sh \
	fac_invld2.sh \
	fac_invld3.sh \
	fac_invld4_rfc5424.sh \
	rawmsg-after-pri.sh \
	rfc5424parser.sh \
	tcp_forwarding_tpl.sh \
	tcp_forwarding_dflt_tpl.sh \
	arrayqueue.sh \
	global_vars.sh \
	da-mainmsg-q.sh \
	validation-run.sh \
	empty-ruleset.sh \
	imtcp-multiport.sh \
	daqueue-persist.sh \
	diskqueue.sh \
	diskqueue-fsync.sh \
	rulesetmultiqueue.sh \
	rulesetmultiqueue-v6.sh \
	manytcp.sh \
	rsf_getenv.sh \
	imtcp_conndrop_tls.sh \
	imtcp_conndrop.sh \
	imtcp_addtlframedelim.sh \
	imtcp_no_octet_counted.sh \
	imtcp_spframingfix.sh \
	sndrcv.sh \
	sndrcv_failover.sh \
	sndrcv_gzip.sh \
	sndrcv_udp.sh \
	sndrcv_udp_nonstdpt.sh \
	sndrcv_udp_nonstdpt_v6.sh \
	imudp_thread_hang.sh \
	sndrcv_udp_nonstdpt_v6.sh \
	asynwr_simple.sh \
	asynwr_simple_2.sh \
	asynwr_timeout.sh \
	asynwr_timeout_2.sh \
	asynwr_small.sh \
	asynwr_tinybuf.sh \
	wr_large_async.sh \
	wr_large_sync.sh \
	asynwr_deadlock.sh \
	asynwr_deadlock_2.sh \
	asynwr_deadlock2.sh \
	asynwr_deadlock4.sh \
	abort-uncleancfg-goodcfg.sh \
	abort-uncleancfg-goodcfg-check.sh \
	abort-uncleancfg-badcfg-check.sh \
	abort-uncleancfg-badcfg-check_1.sh \
	gzipwr_large.sh \
	gzipwr_large_dynfile.sh \
	dynfile_invld_async.sh \
	dynfile_invld_sync.sh \
	dynfile_invalid2.sh \
	complex1.sh \
	queue-persist.sh \
	pipeaction.sh \
	execonlyonce.sh \
	execonlywhenprevsuspended.sh \
	execonlywhenprevsuspended2.sh \
	execonlywhenprevsuspended3.sh \
	execonlywhenprevsuspended4.sh \
	execonlywhenprevsuspended_multiwrkr.sh \
	execonlywhenprevsuspended-queue.sh \
	execonlywhenprevsuspended-nonsusp.sh \
	execonlywhenprevsuspended-nonsusp-queue.sh \
	pipe_noreader.sh \
	dircreate_dflt.sh \
	dircreate_off.sh \
	imuxsock_logger.sh \
	imuxsock_logger_err.sh \
	imuxsock_logger_parserchain.sh \
	imuxsock_traillf.sh \
	imuxsock_ccmiddle.sh \
	imuxsock_logger_root.sh \
	imuxsock_traillf_root.sh \
	imuxsock_ccmiddle_root.sh \
	discard-rptdmsg.sh \
	discard-allmark.sh \
	discard.sh \
	stop.sh \
	failover-async.sh \
	failover-double.sh \
	failover-basic.sh \
	failover-rptd.sh \
	failover-no-rptd.sh \
	failover-no-basic.sh \
	rcvr_fail_restore.sh \
	rscript_contains.sh \
	rscript_field.sh \
	rscript_stop.sh \
	rscript_stop2.sh \
	rscript_prifilt.sh \
	rscript_optimizer1.sh \
	rscript_ruleset_call.sh \
	rscript_set_modify.sh \
	rscript_unaffected_reset.sh \
	rscript_replace_complex.sh \
	rscript_wrap2.sh \
	rscript_wrap3.sh \
	rscript_re_extract.sh \
	rscript_re_match.sh \
	rs_optimizer_pri.sh \
	cee_simple.sh \
	cee_diskqueue.sh \
	incltest.sh \
	incltest_dir.sh \
	incltest_dir_wildcard.sh \
	incltest_dir_empty_wildcard.sh \
	linkedlistqueue.sh \
	lookup_table.sh \
	key_dereference_on_uninitialized_variable_space.sh


if HAVE_VALGRIND
TESTS +=  \
	discard-rptdmsg-vg.sh \
	discard-allmark-vg.sh \
	failover-basic-vg.sh \
	failover-rptd-vg.sh \
	failover-no-basic-vg.sh \
	failover-no-rptd-vg.sh \
	udp-msgreduc-vg.sh \
	udp-msgreduc-orgmsg-vg.sh \
	tcp-msgreduc-vg.sh
endif # HAVE_VALGRIND


if ENABLE_MYSQL_TESTS
TESTS +=  \
	mysql-basic.sh \
	mysql-basic-cnf6.sh \
	mysql-asyn.sh \
	mysql-actq-mt.sh \
	mysql-actq-mt-withpause.sh
if HAVE_VALGRIND
TESTS +=  \
	mysql-basic-vg.sh \
	mysql-asyn-vg.sh \
	mysql-actq-mt-withpause-vg.sh 
endif
if ENABLE_OMLIBDBI
TESTS +=  \
	libdbi-basic.sh \
	libdbi-asyn.sh
if HAVE_VALGRIND
TESTS +=  \
	libdbi-basic-vg.sh
endif
endif
endif

if ENABLE_IMPTCP
# note that some tests simply USE imptcp, but they also
# need to be disabled if we do not have this module
TESTS +=  \
	manyptcp.sh \
	imptcp_large.sh \
	imptcp_addtlframedelim.sh \
	imptcp_conndrop.sh \
	imptcp_no_octet_counted.sh \
	imptcp_spframingfix.sh \
	rscript_random.sh \
	rscript_replace.sh
if HAVE_VALGRIND
TESTS +=  \
	imptcp_conndrop-vg.sh
endif
endif

if ENABLE_ELASTICSEARCH_TESTS
TESTS +=  \
	es-basic.sh \
	es-basic-bulk.sh \
	es-basic-errfile-empty.sh \
	es-basic-errfile-popul.sh \
	es-bulk-errfile-empty.sh \
	es-bulk-errfile-popul.sh 
if ENABLE_IMFILE
TESTS +=  \
	es-bulk-errfile-popul-def-format.sh \
	es-bulk-errfile-popul-erronly.sh \
	es-bulk-errfile-popul-erronly-interleaved.sh \
	es-bulk-errfile-popul-def-interleaved.sh
endif
endif

if ENABLE_MMPSTRUCDATA
TESTS +=  \
	mmpstrucdata.sh
if HAVE_VALGRIND
TESTS +=  \
	mmpstrucdata-vg.sh \
	mmpstrucdata-invalid-vg.sh
endif
endif

if ENABLE_MMNORMALIZE
if ENABLE_IMPTCP
TESTS +=  \
	mmnormalize_regex_defaulted.sh \
	mmnormalize_regex_disabled.sh \
	mmnormalize_variable.sh \
	mmnormalize_tokenized.sh
endif
if LOGNORM_REGEX_SUPPORTED
TESTS += \
	mmnormalize_regex.sh
endif
endif

if ENABLE_MMJSONPARSE
if ENABLE_IMPTCP
TESTS +=  \
	mmjsonparse_simple.sh \
	mmjsonparse_cim.sh \
	json_array_subscripting.sh \
	json_array_looping.sh \
	json_nonarray_looping.sh
endif
if HAVE_VALGRIND
TESTS +=  \
	json_null_array-vg.sh \
	json_null-vg.sh
endif
TESTS +=  \
	stop_when_array_has_element.sh \
	json_null_array.sh \
	json_null.sh
endif

if ENABLE_GNUTLS
# TODO: re-enable in newer version
#TESTS +=  \
#sndrcv_tls_anon.sh \
#sndrcv_tls_anon_rebind.sh \
imtcp-tls-basic.sh
if HAVE_VALGRIND
TESTS += \
	imtcp-tls-basic-vg.sh \
	imtcp_conndrop_tls-vg.sh
if !ENABLE_DISTCHECK_WORKAROUND
	manytcp-too-few-tls-vg.sh
endif
endif
endif

if ENABLE_OMUXSOCK
TESTS += uxsock_simple.sh
endif

if ENABLE_RELP
TESTS += sndrcv_relp.sh
endif

if ENABLE_OMUDPSPOOF
TESTS += \
	sndrcv_omudpspoof.sh \
	sndrcv_omudpspoof_nonstdpt.sh
endif

if ENABLE_OMSTDOUT
TESTS += \
	omod-if-array.sh \
	threadingmq.sh \
	threadingmqaq.sh \
	badqi.sh
if ENABLE_IMPTCP
TESTS += \
	tabescape_dflt.sh \
	tabescape_off.sh \
	timestamp.sh \
	inputname.sh \
	proprepltest.sh \
	parsertest.sh \
	fieldtest.sh
endif
endif

if ENABLE_OMRULESET
TESTS += \
	omruleset.sh \
	omruleset-queue.sh
endif

if ENABLE_EXTENDED_TESTS
# random.sh is temporarily disabled as it needs some work
# to rsyslog core to complete in reasonable time
#TESTS += random.sh 
endif

if ENABLE_IMFILE
TESTS += \
	imfile-basic.sh \
	imfile-readmode2.sh \
	imfile-readmode2-with-persists-data-during-stop.sh \
	imfile-readmode2-with-persists.sh \
	imfile-endregex.sh
if HAVE_VALGRIND
TESTS += \
	imfile-basic-vg.sh \
	imfile-endregex-vg.sh \
	imfile-readmode2-vg.sh
endif
endif

endif # if ENABLE_TESTBENCH

TESTS_ENVIRONMENT = RSYSLOG_MODDIR='$(abs_top_builddir)'/runtime/.libs/
DISTCLEANFILES=rsyslog.pid
test_files = testbench.h runtime-dummy.c

EXTRA_DIST= \
	1.rstest 2.rstest 3.rstest err1.rstest \
	validation-run.sh \
	tls-certs/ca-key.pem \
	tls-certs/ca.pem \
	tls-certs/cert.pem \
	tls-certs/key.pem \
	testsuites/x.509/ca.pem \
	testsuites/x.509/ca-key.pem \
	testsuites/x.509/client-cert.pem \
	testsuites/x.509/client-key.pem \
	testsuites/x.509/machine-cert.pem \
	testsuites/x.509/machine-key.pem \
	testsuites/invalid.conf \
	testsuites/valid.conf \
	cfg.sh \
	cfg1.cfgtest \
	cfg1.testin \
	cfg2.cfgtest \
	cfg2.testin \
	cfg3.cfgtest \
	cfg3.testin \
	cfg4.cfgtest \
	cfg4.testin \
	DevNull.cfgtest \
	err1.rstest \
	NoExistFile.cfgtest \
	timestamp.sh \
	testsuites/ts3164.conf \
	testsuites/mon1digit.ts3164 \
	testsuites/mon2digit.ts3164 \
	testsuites/Jan.ts3164 \
	testsuites/Feb.ts3164 \
	testsuites/Mar.ts3164 \
	testsuites/Apr.ts3164 \
	testsuites/May.ts3164 \
	testsuites/Jun.ts3164 \
	testsuites/Jul.ts3164 \
	testsuites/Aug.ts3164 \
	testsuites/Sep.ts3164 \
	testsuites/Oct.ts3164 \
	testsuites/Nov.ts3164 \
	testsuites/Dec.ts3164 \
	testsuites/ts3339.conf \
	testsuites/master.ts3339 \
	testsuites/tsmysql.conf \
	testsuites/master.tsmysql \
	testsuites/tspgsql.conf \
	testsuites/master.tspgsql \
	testsuites/subsecond.conf \
	testsuites/master.subsecond \
	testsuites/parse_8bit_escape.conf \
	testsuites/8bit.parse_8bit_escape \
	testsuites/parse1.conf \
	testsuites/field1.conf \
	testsuites/1.parse1 \
	testsuites/2.parse1 \
	testsuites/3.parse1 \
	testsuites/4.parse1 \
	testsuites/mark.parse1 \
	testsuites/8bit.parse1 \
	testsuites/empty.parse1 \
	testsuites/snare.parse1 \
	testsuites/oversizeTag-1.parse1 \
	testsuites/weird.parse1 \
	testsuites/date1.parse1 \
	testsuites/date2.parse1 \
	testsuites/date3.parse1 \
	testsuites/date4.parse1 \
	testsuites/date5.parse1 \
	testsuites/rfc3164.parse1 \
	testsuites/rfc5424-1.parse1 \
	testsuites/rfc5424-2.parse1 \
	testsuites/rfc5424-3.parse1 \
	testsuites/rfc5424-4.parse1 \
	testsuites/malformed1.parse1 \
	testsuites/reallife.parse1 \
	testsuites/parse2.conf \
	testsuites/reallife.parse2 \
	testsuites/parse3.conf \
	testsuites/reallife.parse3 \
	testsuites/parse-nodate.conf \
	testsuites/samples.parse-nodate \
	testsuites/parse_invld_regex.conf \
	testsuites/samples.parse_invld_regex \
	testsuites/parse-3164-buggyday.conf \
	testsuites/samples.parse-3164-buggyday \
	testsuites/snare_ccoff_udp.conf \
	testsuites/samples.snare_ccoff_udp \
	testsuites/snare_ccoff_udp2.conf \
	testsuites/samples.snare_ccoff_udp2 \
	testsuites/omod-if-array.conf \
	testsuites/1.omod-if-array \
	testsuites/1.field1 \
	tcp_forwarding_tpl.sh \
	testsuites/tcp_forwarding_tpl.conf \
	tcp_forwarding_dflt_tpl.sh \
	testsuites/tcp_forwarding_dflt_tpl.conf \
	killrsyslog.sh \
	parsertest.sh \
	fieldtest.sh \
	rsf_getenv.sh \
	testsuites/rsf_getenv.conf \
	diskqueue.sh \
	testsuites/diskqueue.conf \
	arrayqueue.sh \
	testsuites/arrayqueue.conf \
	rscript_contains.sh \
	testsuites/rscript_contains.conf \
	rscript_field.sh \
	testsuites/rscript_field.conf \
	rscript_stop.sh \
	testsuites/rscript_stop.conf \
	rscript_stop2.sh \
	testsuites/rscript_stop2.conf \
	stop.sh \
	testsuites/stop.conf \
	rscript_le.sh \
	testsuites/rscript_le.conf \
	rscript_ge.sh \
	testsuites/rscript_ge.conf \
	rscript_lt.sh \
	testsuites/rscript_lt.conf \
	rscript_gt.sh \
	testsuites/rscript_gt.conf \
	rscript_ne.sh \
	testsuites/rscript_ne.conf \
	rscript_eq.sh \
	testsuites/rscript_eq.conf \
	rscript_set_modify.sh \
	testsuites/rscript_set_modify.conf \
	testsuites/rscript_unaffected_reset.conf \
	stop-localvar.sh \
	testsuites/stop-localvar.conf \
	stop-msgvar.sh \
	testsuites/stop-msgvar.conf \
	msgvar-concurrency.sh \
	testsuites/msgvar-concurrency.conf \
	localvar-concurrency.sh \
	testsuites/localvar-concurrency.conf \
	global_vars.sh \
	testsuites/global_vars.conf \
	rfc5424parser.sh \
	testsuites/rfc5424parser.conf \
	fac_authpriv.sh \
	testsuites/fac_authpriv.conf \
	fac_local0.sh \
	testsuites/fac_local0.conf \
	fac_local7.sh \
	testsuites/fac_local7.conf \
	fac_mail.sh \
	testsuites/fac_mail.conf \
	fac_news.sh \
	testsuites/fac_news.conf \
	fac_ftp.sh \
	testsuites/fac_ftp.conf \
	fac_ntp.sh \
	testsuites/fac_ntp.conf \
	fac_uucp.sh \
	testsuites/fac_uucp.conf \
	fac_invld1.sh \
	testsuites/fac_invld1.conf \
	fac_invld2.sh \
	testsuites/fac_invld2.conf \
	fac_invld3.sh \
	testsuites/fac_invld3.conf \
	fac_invld4_rfc5424.sh \
	testsuites/fac_invld4_rfc5424.conf \
	rawmsg-after-pri.sh \
	testsuites/rawmsg-after-pri.conf \
	rs_optimizer_pri.sh \
	testsuites/rs_optimizer_pri.conf \
	rscript_prifilt.sh \
	testsuites/rscript_prifilt.conf \
	rscript_optimizer1.sh \
	testsuites/rscript_optimizer1.conf \
	rscript_ruleset_call.sh \
	testsuites/rscript_ruleset_call.conf \
	cee_simple.sh \
	testsuites/cee_simple.conf \
	cee_diskqueue.sh \
	testsuites/cee_diskqueue.conf \
	mmjsonparse_simple.sh \
	testsuites/mmjsonparse_simple.conf \
	mmjsonparse_cim.sh \
	testsuites/mmjsonparse_cim.conf \
	incltest.sh \
	testsuites/incltest.conf \
	incltest_dir.sh \
	testsuites/incltest_dir.conf \
	incltest_dir_empty_wildcard.sh \
	testsuites/incltest_dir_empty_wildcard.conf \
	incltest_dir_wildcard.sh \
	testsuites/incltest_dir_wildcard.conf \
	testsuites/incltest.d/include.conf \
	es-basic.sh \
	testsuites/es-basic.conf \
	es-basic-bulk.sh \
	testsuites/es-basic-bulk.conf \
	es-basic-errfile-empty.sh \
	testsuites/es-basic-errfile-empty.conf \
	es-basic-errfile-popul.sh \
	testsuites/es-basic-errfile-popul.conf \
	es-bulk-errfile-empty.sh \
	testsuites/es-bulk-errfile-empty.conf \
	es-bulk-errfile-popul.sh \
	testsuites/es-bulk-errfile-popul.conf \
	es-bulk-errfile-popul-def-format.sh \
	testsuites/es-bulk-errfile-popul-def-format.conf \
	es-bulk-errfile-popul-erronly.sh \
	testsuites/es-bulk-errfile-popul-erronly.conf \
	es-bulk-errfile-popul-erronly-interleaved.sh \
	testsuites/es-bulk-errfile-popul-erronly-interleaved.conf \
	es-bulk-errfile-popul-def-interleaved.sh \
	testsuites/es-bulk-errfile-popul-def-interleaved.conf \
	linkedlistqueue.sh \
	testsuites/linkedlistqueue.conf \
	da-mainmsg-q.sh \
	testsuites/da-mainmsg-q.conf \
	diskqueue-fsync.sh \
	testsuites/diskqueue-fsync.conf \
	empty-ruleset.sh \
	testsuites/empty-ruleset.conf \
	imtcp-tls-basic.sh \
	imtcp-tls-basic-vg.sh \
	testsuites/imtcp-tls-basic.conf \
	imtcp-multiport.sh \
	testsuites/imtcp-multiport.conf \
	udp-msgreduc-orgmsg-vg.sh \
	testsuites/udp-msgreduc-orgmsg-vg.conf \
	udp-msgreduc-vg.sh \
	testsuites/udp-msgreduc-vg.conf \
	manytcp-too-few-tls-vg.sh \
	testsuites/manytcp-too-few-tls.conf \
	manytcp.sh \
	testsuites/manytcp.conf \
	manyptcp.sh \
	testsuites/manyptcp.conf \
	imptcp_large.sh \
	testsuites/imptcp_large.conf \
	imptcp_addtlframedelim.sh \
	testsuites/imptcp_addtlframedelim.conf \
	imptcp_conndrop-vg.sh \
	imptcp_conndrop.sh \
	testsuites/imptcp_conndrop.conf \
	imptcp_no_octet_counted.sh \
	testsuites/imptcp_no_octet_counted.conf \
	testsuites/no_octet_counted.testdata \
	imtcp_no_octet_counted.sh \
	testsuites/imtcp_no_octet_counted.conf \
	testsuites/spframingfix.testdata \
	imtcp_spframingfix.sh \
	testsuites/imtcp_spframingfix.conf \
	imptcp_spframingfix.sh \
	testsuites/imptcp_spframingfix.conf \
	imtcp_conndrop.sh \
	testsuites/imtcp_conndrop.conf \
	imtcp_conndrop_tls.sh \
	imtcp_conndrop_tls-vg.sh \
	testsuites/imtcp_conndrop.conf \
	imtcp_addtlframedelim.sh \
	testsuites/imtcp_addtlframedelim.conf \
	tcp-msgreduc-vg.sh \
	testsuites/./tcp-msgreduc-vg.conf \
	inputname.sh \
	testsuites/inputname_imtcp.conf \
	testsuites/1.inputname_imtcp_12514 \
	testsuites/1.inputname_imtcp_12515 \
	testsuites/1.inputname_imtcp_12516 \
	omod-if-array.sh \
	discard.sh \
	testsuites/discard.conf \
	failover-no-rptd.sh \
	failover-no-rptd-vg.sh \
	testsuites/failover-no-rptd.conf \
	failover-no-basic.sh \
	failover-no-basic-vg.sh \
	testsuites/failover-no-basic.conf \
	failover-rptd.sh \
	failover-rptd-vg.sh \
	testsuites/failover-rptd.conf \
	failover-basic.sh \
	failover-basic-vg.sh \
	testsuites/failover-basic.conf \
	failover-async.sh \
	testsuites/failover-async.conf \
	failover-double.sh \
	testsuites/failover-double.conf \
	discard-rptdmsg.sh \
	discard-rptdmsg-vg.sh \
	testsuites/discard-rptdmsg.conf \
	discard-allmark.sh \
	discard-allmark-vg.sh \
	testsuites/discard-allmark.conf \
	diag.sh \
	testsuites/diag-common.conf \
	testsuites/diag-common2.conf \
	rcvr_fail_restore.sh \
	testsuites/rcvr_fail_restore_rcvr.conf \
	testsuites/rcvr_fail_restore_sender.conf \
	daqueue-persist.sh \
	daqueue-persist-drvr.sh \
	queue-persist.sh \
	queue-persist-drvr.sh \
	testsuites/queue-persist.conf \
	threadingmq.sh \
	testsuites/threadingmq.conf \
	threadingmqaq.sh \
	testsuites/threadingmqaq.conf \
	sndrcv_drvr.sh \
	sndrcv_drvr_noexit.sh \
	sndrcv_failover.sh \
	testsuites/sndrcv_failover_sender.conf \
	testsuites/sndrcv_failover_rcvr.conf \
	sndrcv.sh \
	testsuites/sndrcv_sender.conf \
	testsuites/sndrcv_rcvr.conf \
	sndrcv_relp.sh \
	testsuites/sndrcv_relp_sender.conf \
	testsuites/sndrcv_relp_rcvr.conf \
	sndrcv_udp.sh \
	testsuites/sndrcv_udp_sender.conf \
	testsuites/sndrcv_udp_rcvr.conf \
	imudp_thread_hang.sh \
	testsuites/imudp_thread_hang.conf \
	sndrcv_udp_nonstdpt.sh \
	testsuites/sndrcv_udp_nonstdpt_sender.conf \
	testsuites/sndrcv_udp_nonstdpt_rcvr.conf \
	sndrcv_udp_nonstdpt_v6.sh \
	testsuites/sndrcv_udp_nonstdpt_v6_sender.conf \
	testsuites/sndrcv_udp_nonstdpt_v6_rcvr.conf \
	sndrcv_omudpspoof.sh \
	testsuites/sndrcv_omudpspoof_sender.conf \
	testsuites/sndrcv_omudpspoof_rcvr.conf \
	sndrcv_omudpspoof_nonstdpt.sh \
	testsuites/sndrcv_omudpspoof_nonstdpt_sender.conf \
	testsuites/sndrcv_omudpspoof_nonstdpt_rcvr.conf \
	sndrcv_gzip.sh \
	testsuites/sndrcv_gzip_sender.conf \
	testsuites/sndrcv_gzip_rcvr.conf \
	pipeaction.sh \
	testsuites/pipeaction.conf \
	pipe_noreader.sh \
	testsuites/pipe_noreader.conf \
	uxsock_simple.sh \
	testsuites/uxsock_simple.conf \
	asynwr_simple.sh \
	testsuites/asynwr_simple.conf \
	asynwr_simple_2.sh \
	testsuites/asynwr_simple_2.conf \
	asynwr_timeout.sh \
	testsuites/asynwr_timeout.conf \
	asynwr_timeout_2.sh \
	testsuites/asynwr_timeout_2.conf \
	asynwr_small.sh \
	testsuites/asynwr_small.conf \
	asynwr_tinybuf.sh \
	testsuites/asynwr_tinybuf.conf \
	wr_large_async.sh \
	wr_large_sync.sh \
	wr_large.sh \
	testsuites/wr_large.conf \
	asynwr_deadlock.sh \
	testsuites/asynwr_deadlock.conf \
	asynwr_deadlock_2.sh \
	testsuites/asynwr_deadlock_2.conf \
	asynwr_deadlock2.sh \
	testsuites/asynwr_deadlock2.conf \
	asynwr_deadlock4.sh \
	testsuites/asynwr_deadlock4.conf \
	abort-uncleancfg-goodcfg.sh \
	testsuites/abort-uncleancfg-goodcfg.conf \
	abort-uncleancfg-goodcfg-check.sh \
	testsuites/abort-uncleancfg-goodcfg.conf \
	abort-uncleancfg-badcfg-check.sh \
	testsuites/abort-uncleancfg-badcfg.conf \
	abort-uncleancfg-badcfg-check_1.sh \
	testsuites/abort-uncleancfg-badcfg_1.conf \
	gzipwr_large.sh \
	testsuites/gzipwr_large.conf \
	gzipwr_large_dynfile.sh \
	testsuites/gzipwr_large_dynfile.conf \
	complex1.sh \
	testsuites/complex1.conf \
	random.sh \
	testsuites/random.conf \
	imfile-readmode2.sh \
	imfile-readmode2-vg.sh \
	imfile-readmode2-with-persists-data-during-stop.sh \
	imfile-readmode2-with-persists.sh \
	testsuites/imfile-readmode2.conf \
	testsuites/imfile-readmode2-with-persists.conf \
	testsuites/imfile-readmode2-with-persists-data-during-stop.conf \
	imfile-endregex.sh \
	imfile-endregex-vg.sh \
	testsuites/imfile-endregex.conf \
	imfile-basic.sh \
	imfile-basic-vg.sh \
	testsuites/imfile-basic.conf \
	dynfile_invld_async.sh \
	dynfile_invld_sync.sh \
	dynfile_cachemiss.sh \
	testsuites/dynfile_cachemiss.conf \
	dynfile_invalid2.sh \
	testsuites/dynfile_invalid2.conf \
	proprepltest.sh \
	testsuites/rfctag.conf \
	testsuites/master.rfctag \
	testsuites/nolimittag.conf \
	testsuites/master.nolimittag \
	rulesetmultiqueue.sh \
	testsuites/rulesetmultiqueue.conf \
	rulesetmultiqueue-v6.sh \
	testsuites/rulesetmultiqueue-v6.conf \
	omruleset.sh \
	testsuites/omruleset.conf \
	omruleset-queue.sh \
	testsuites/omruleset-queue.conf \
	badqi.sh \
	testsuites/badqi.conf \
	bad_qi/dbq.qi \
	execonlyonce.sh \
	testsuites/execonlyonce.conf \
	testsuites/execonlyonce.data \
	execonlywhenprevsuspended.sh \
	testsuites/execonlywhenprevsuspended.conf \
	execonlywhenprevsuspended2.sh \
	testsuites/execonlywhenprevsuspended2.conf \
	execonlywhenprevsuspended3.sh \
	testsuites/execonlywhenprevsuspended3.conf \
	execonlywhenprevsuspended4.sh \
	testsuites/execonlywhenprevsuspended4.conf \
	execonlywhenprevsuspended_multiwrkr.sh \
	testsuites/execonlywhenprevsuspended_multiwrkr.conf \
	execonlywhenprevsuspended-queue.sh \
	testsuites/execonlywhenprevsuspended-queue.conf \
	execonlywhenprevsuspended-nonsusp.sh \
	testsuites/execonlywhenprevsuspended-nonsusp.conf \
	execonlywhenprevsuspended-nonsusp-queue.sh \
	testsuites/execonlywhenprevsuspended-nonsusp-queue.conf \
	tabescape_dflt.sh \
	testsuites/tabescape_dflt.conf \
	testsuites/1.tabescape_dflt \
	tabescape_off.sh \
	testsuites/tabescape_off.conf \
	testsuites/1.tabescape_off \
	dircreate_dflt.sh \
	testsuites/dircreate_dflt.conf \
	dircreate_off.sh \
	testsuites/dircreate_off.conf \
	imuxsock_logger_parserchain.sh \
	testsuites/imuxsock_logger_parserchain.conf \
	imuxsock_logger.sh \
	testsuites/imuxsock_logger.conf \
	imuxsock_logger_err.sh \
	imuxsock_logger_root.sh \
	testsuites/imuxsock_logger_root.conf \
	resultdata/imuxsock_logger.log \
	imuxsock_traillf.sh \
	testsuites/imuxsock_traillf.conf \
	imuxsock_traillf_root.sh \
	testsuites/imuxsock_traillf_root.conf \
	resultdata/imuxsock_traillf.log \
	imuxsock_ccmiddle.sh \
	testsuites/imuxsock_ccmiddle.conf \
	imuxsock_ccmiddle_root.sh \
	testsuites/imuxsock_ccmiddle_root.conf \
	resultdata/imuxsock_ccmiddle.log \
	imuxsock_hostname.sh \
	testsuites/imuxsock_hostname.conf \
	resultdata/imuxsock_hostname.log \
	testsuites/mysql-truncate.sql \
	testsuites/mysql-select-msg.sql \
	libdbi-basic.sh \
	testsuites/libdbi-basic.conf \
	libdbi-asyn.sh \
	testsuites/libdbi-asyn.conf \
	mysql-basic.sh \
	mysql-basic-cnf6.sh \
	mysql-basic-vg.sh \
	testsuites/mysql-basic.conf \
	testsuites/mysql-basic-cnf6.conf \
	mysql-asyn.sh \
	mysql-asyn-vg.sh \
	testsuites/mysql-asyn.conf \
	mysql-actq-mt.sh \
	mysql-actq-mt-withpause.sh \
	mysql-actq-mt-withpause-vg.sh \
	testsuites/mysql-actq-mt.conf \
	mmpstrucdata.sh \
        mmpstrucdata-vg.sh \
	testsuites/mmpstrucdata.conf \
	mmpstrucdata-invalid-vg.sh \
	testsuites/mmpstrucdata-invalid.conf \
	libdbi-basic-vg.sh \
	mmnormalize_variable.sh \
	mmnormalize_tokenized.sh \
	testsuites/mmnormalize_variable.conf \
	testsuites/mmnormalize_variable.rulebase \
	testsuites/date_time_msg \
	testsuites/mmnormalize_tokenized.conf \
	testsuites/mmnormalize_tokenized.rulebase \
	testsuites/tokenized_input \
	rscript_random.sh \
	testsuites/rscript_random.conf \
	rscript_replace.sh \
	testsuites/rscript_replace.conf \
	rscript_replace_complex.sh \
	testsuites/rscript_replace_complex.conf \
	testsuites/complex_replace_input \
	rscript_unaffected_reset.sh \
	rscript_wrap2.sh \
	testsuites/rscript_wrap2.conf \
	rscript_wrap3.sh \
	testsuites/rscript_wrap3.conf \
	testsuites/wrap3_input\
	testsuites/gethostname.conf \
	json_array_subscripting.sh \
	testsuites/json_array_subscripting.conf \
	testsuites/json_array_input \
	testsuites/json_nonarray_input \
	json_array_looping.sh \
	json_nonarray_looping.sh \
	testsuites/json_array_looping.conf \
	mmnormalize_regex.sh \
	testsuites/mmnormalize_regex.conf \
	testsuites/mmnormalize_regex.rulebase \
	testsuites/regex_input \
	mmnormalize_regex_disabled.sh \
	testsuites/mmnormalize_regex_disabled.conf \
	mmnormalize_regex_defaulted.sh \
	testsuites/mmnormalize_regex_defaulted.conf \
	stop_when_array_has_element.sh \
	testsuites/stop_when_array_has_elem_input \
	testsuites/stop_when_array_has_element.conf \
	key_dereference_on_uninitialized_variable_space.sh \
	testsuites/key_dereference_on_uninitialized_variable_space.conf \
	rscript_re_extract.sh \
	testsuites/rscript_re_extract.conf \
	rscript_re_match.sh \
	testsuites/rscript_re_match.conf \
	lookup_table.sh \
	testsuites/lookup_table.conf \
	testsuites/xlate.lkp_tbl \
	testsuites/xlate_more.lkp_tbl \
	cfg.sh

# TODO: re-enable
#sndrcv_tls_anon_rebind.sh \
#testsuites/sndrcv_tls_anon_rebind_sender.conf \
#testsuites/sndrcv_tls_anon_rebind_rcvr.conf \
#sndrcv_tls_anon.sh \
#testsuites/sndrcv_tls_anon_sender.conf \
#testsuites/sndrcv_tls_anon_rcvr.conf \
#

ourtail_SOURCES = ourtail.c
msleep_SOURCES = msleep.c
chkseq_SOURCES = chkseq.c

uxsockrcvr_SOURCES = uxsockrcvr.c
uxsockrcvr_LDADD = $(SOL_LIBS)

tcpflood_SOURCES = tcpflood.c
tcpflood_CPPFLAGS = $(PTHREADS_CFLAGS) $(GNUTLS_CFLAGS)
tcpflood_LDADD = $(SOL_LIBS) $(PTHREADS_LIBS) $(GNUTLS_LIBS)
if ENABLE_GNUTLS
tcpflood_LDADD += -lgcrypt
endif

minitcpsrv_SOURCES = minitcpsrvr.c
minitcpsrv_LDADD = $(SOL_LIBS)

syslog_caller_SOURCES = syslog_caller.c
syslog_caller_CPPFLAGS = $(LIBLOGGING_STDLOG_CFLAGS)
syslog_caller_LDADD = $(SOL_LIBS) $(LIBLOGGING_STDLOG_LIBS)

diagtalker_SOURCES = diagtalker.c
diagtalker_LDADD = $(SOL_LIBS)

randomgen_SOURCES = randomgen.c
randomgen_LDADD = $(SOL_LIBS)

inputfilegen_SOURCES = inputfilegen.c
inputfilegen_LDADD = $(SOL_LIBS)

nettester_SOURCES = nettester.c getline.c
nettester_LDADD = $(SOL_LIBS)

# rtinit tests disabled for the moment - also questionable if they
# really provide value (after all, everything fails if rtinit fails...)
#rt_init_SOURCES = rt-init.c $(test_files)
#rt_init_CPPFLAGS =  -I$(top_srcdir) $(PTHREADS_CFLAGS) $(RSRT_CFLAGS)
#rt_init_LDADD = $(RSRT_LIBS) $(ZLIB_LIBS) $(PTHREADS_LIBS) $(SOL_LIBS)
#rt_init_LDFLAGS = -export-dynamic

# same for basic rscript tests
#rscript_SOURCES = rscript.c getline.c $(test_files)
#rscript_CPPFLAGS =  -I$(top_srcdir) $(PTHREADS_CFLAGS) $(RSRT_CFLAGS)
#rscript_LDADD = $(RSRT_LIBS) $(ZLIB_LIBS) $(PTHREADS_LIBS) $(SOL_LIBS)
#rscript_LDFLAGS = -export-dynamic
