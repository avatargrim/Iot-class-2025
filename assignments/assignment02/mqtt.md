# Exploring MQTT QoS Levels

Experiment with QoS 0, 1, and 2.
Observe how message delivery changes based on QoS settings.

## Publisher_qos.py output

```
[15:45:37] DEBUG | Sending CONNECT (u0, p0, wr0, wq0, wf0, c1, k60) client_id=b''
Enter message to publish: [15:45:37] DEBUG | Received CONNACK (0, 0)
yipeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeee
Enter QoS level (0, 1, 2): 2
[15:45:46] DEBUG | Sending PUBLISH (d0, q2, r0, m1), 'b'test/qos/6510301032/temperature'', ... (69 bytes)
[15:45:46] PUBLISH REQUESTED | QoS=2 | Message='yipeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeee' | msgid=1
Enter message to publish: [15:45:46] DEBUG | Received PUBREC (Mid: 1)
[15:45:46] DEBUG | Sending PUBREL (Mid: 1)
[15:45:46] DEBUG | Received PUBCOMP (Mid: 1)
[15:45:46] PUBLISHED | msgid=1
```

## Subscriber_qos.py Output

```
c:\Users\User\Desktop\LabIOT\Iot-class-2025-gateway\app\subscriber_qos.py:25: DeprecationWarning: Callback API version 1 is deprecated, update to latest version
  client = mqtt.Client()
[15:45:27] DEBUG | Sending CONNECT (u0, p0, wr0, wq0, wf0, c1, k60) client_id=b''
[15:45:27] DEBUG | Received CONNACK (0, 0)
[15:45:27] Connected with result code 0
[15:45:27] DEBUG | Sending SUBSCRIBE (d0, m1) [(b'test/qos/6510301032/#', 2)]
[15:45:27] DEBUG | Received SUBACK
[15:45:46] DEBUG | Received PUBLISH (d0, q2, r0, m1), 'test/qos/6510301032/temperature', ...  (69 bytes)
[15:45:46] DEBUG | Sending PUBREC (Mid: 1)
[15:45:46] DEBUG | Received PUBREL (Mid: 1)
[15:45:46] RECEIVED | QoS=2 | Topic=test/qos/6510301032/temperature | Message=yipeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeee | msgid=1
[15:45:46] DEBUG | Sending PUBCOMP (Mid: 1)
[15:46:28] DEBUG | Sending PINGREQ
[15:46:28] DEBUG | Received PINGRESP
```