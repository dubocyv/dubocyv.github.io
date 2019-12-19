PATH=/bin:/usr/bin:/apps/chkapp/bin:$(HOME)/bin:.

all :		data.json
#		@ chcon -R -v -t httpd_sys_rw_content_t * >/dev/null; chmod a+r *;

rebuild: clean data.json

clean:
	rm -f data.json;

data.json: data.txt
	@umask 002;
	[ -s data.txt ] && { if txt2json < data.txt > $@ ; then touch -r data.txt $@; else rm -f $@; fi }
