| NAME               | ID         | ADVPROG CLASS |
| ------------------ | ---------- | ------------- |
| Sultan Ibnu Mansiz | 2306275840 | B             |

# Module 9: Software Architecture - Reflection

## 1. How much data your publisher program will send to the message broker in one run? 
In this implementation, the publisher transmits five data messages per execution, with each message including a unique user ID and its associated name, resulting in a total of five user records.

## 2. The url of: *“amqp://guest:guest@localhost:5672”* is the same as in the subscriber program, what does it mean?
This suggests that the publisher and subscriber are linked to the same RabbitMQ server instance, utilizing identical authentication credentials and the same network endpoint. This configuration enables seamless message exchange through a shared broker.

---

### Running RabbitMQ
![RabbitMQ](images/RunningRabbitMQ.png)

### Sending and Processing Event
![Events](images/Events.png)
When the publisher runs, it sends five data messages to the RabbitMQ server. Since the subscriber is continuously listening to the server, it captures these messages and processes them based on the specified format.

### RabbitMQ Chart when Running the Event
![MonitoringChart](images/MonitoringChart.png)
The monitoring chart displays two distinct purple spikes, indicating that two messages were successfully sent and acknowledged by the consumer. This confirms that the subscriber received and processed these messages. The lack of yellow spikes suggests either minimal message publishing activity or that such events were not recorded within the chart’s observed timeframe.