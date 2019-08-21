Generated with these steps:

```sh
macbook$ mkdir filebeat-arm-bin && cd filebeat-arm-bin
macbook$ docker run -it --rm -v `pwd`:/build golang:1.8.3 /bin/bash
root@1465b1675279:/go# go get github.com/elastic/beats       
package github.com/elastic/beats: no buildable Go source files in /go/src/github.com/elastic/beats
root@1465b1675279:/go# cd /go/src/github.com/elastic/beats/filebeat/
root@1465b1675279:/go# git checkout v5.6.3
root@1465b1675279:/go/src/github.com/elastic/beats/filebeat# GOARCH=arm go build
root@1465b1675279:/go/src/github.com/elastic/beats/filebeat# cp filebeat /build
root@1465b1675279:/go/src/github.com/elastic/beats/filebeat# exit
exit
macbook$ file filebeat 
filebeat: ELF 32-bit LSB executable, ARM, EABI5 version 1 (SYSV), statically linked, not stripped
```

Source: https://discuss.elastic.co/t/how-to-install-filebeat-on-a-arm-based-sbc-eg-raspberry-pi-3/103670/3
