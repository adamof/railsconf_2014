AMQP (advanced message queuing protocol)
- blind pipe
- fast
- open
- centralized
- message: headers + bodies
- conventions that map easily to http concepts
- supports the RPC messaging pattern

Rack-AMQP
- serves Rack applications over AMQP

Jackalope ?
- they deploy with this

Shows a comparison table between HTTP and AMQP

RabbitMQ:
- open source AMQP broker

AMQParty - API compatibable with HTTParty

Rack::AMQP::Client (built in top of bunny)

Benchmarks using AMQParty and HTTParty (2.9sec vs 3.6secs) 
