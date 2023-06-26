# ssh-logstash-pipeline

[![CI](https://github.com/netways/ssh-logstash-pipeline/workflows/Logstash%20Syntax/badge.svg?event=push)](https://github.com/netways/ssh-logstash-pipeline/actions?query=workflow%3A%22Logstash+Syntax%22)

## Input and Output

This pipeline does not provide inputs or outputs so you can configure whatever you need. Files named `input.conf` and `output.conf` will not interfere with updates via git, so name your files accordingly.

Here are examples how your files could look if you want to use a local Redis instance.

```
input {
  redis {
    host => localhost
    key => "ssh"
    data_type => list
  }
}

output {
  redis {
    key => "forwarder"
    data_type => list
    host => localhost
  }
}
```
