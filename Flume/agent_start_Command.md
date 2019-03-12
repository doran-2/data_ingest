flume-ng agent \
--conf /etc/flume-ng/conf \
--conf-file $DEVSH/exercises/flume/Netcat.conf \
--name agent1 -Dflume.root.logger=INFO,console 