# Logging an .NET Core Web API with Serilog in ElasticSearch + Kibana and Docker

Serilog is often referred to as the new logging framework on the .NET platform. 
Provides structured logging that can be delivered or stored in several [sinks](https://github.com/serilog/serilog/wiki/Provided-Sinks#list-of-available-sinks) like Elasticsearch, RabbitMQ, Datadog, etc.
In this case we are using ElasticSearch as a database and kibana for data visualization.

To try out locally the project:

If you run the project with docker-compose this will raise:
* Elasticsearch in http://localhost:9200
* Kibana in http://localhost:5601
* .NET Web API in https://localhost:44400

Now you can send some request to the GET endpoint: https://localhost:44400/weatherforecast
At this poin the application would have logged a few events to ElasticSearch.
Let's open up Kibana. You need to create an index pattern before you can view de logged data.
To do this, click the Discover link in the navigation, and then copy and paste the logstash index name which should be listed toward the bottom of the page into the index textbox and click the next step button.
Then, specify the time filter field name by selecting the @timestamp field and click the Create index pattern button.
You can now view the logs by clicking the Discover link in the navigation pane.

## Resources:
Here are some resources that helped me to set up the project:
* [Serilog](https://serilog.net/)
* [Serilog.AspNetCore](https://github.com/serilog/serilog-aspnetcore)
* [Logging with ElasticSearch, Kibana, ASP.NET Core and Docker](https://www.humankode.com/asp-net-core/logging-with-elasticsearch-kibana-asp-net-core-and-docker)
