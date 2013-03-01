# check-logstash

This is a simple check script for the monitoring tools Bloonix or Nagios.

    input {
        file {
            type => "check-logstash"
            path => "/var/log/logstash/monitor.in"
        }
    }

    filter {
        .. do something with the events just for testing ..
    }

    output {
        file {
            type => "check-logstash"
            path => "/var/log/logstash/monitor.out"
        }
    }

The script check-logstash writes every time it is called a event to the file monitor.in.

Logstash should reads the file and forward the message filtered to the file monitor.out.

You can set a timeout in seconds when logstash has to process new events from monitor.in.
