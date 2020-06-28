# 🔥OSI Model

<img alt="OSI Model" width="700px" src="/assets/images/osi2.png" />

---

<img alt="OSI Model" width="700px" src="/assets/images/osi.jpg" />

---

<img alt="OSI Model" width="600px" src="/assets/images/osi.webp" />

?> The **Open Systems Interconnection (OSI)** model provides a standard for different computer systems to be able to communicate with each other.

?> The OSI model can be seen as a universal language for computer networking. It’s based on the concept of splitting up a communication system into **seven abstract layers**, each one stacked upon the last. Each layer of the OSI model handles a specific job and communicates with the layers above and below itself.

!> Although the modern Internet doesn’t strictly follow the OSI model (it more closely follows the simpler Internet protocol suite), the OSI model is still very useful for troubleshooting network problems. If the problem can be narrowed down to one specific layer of the model, a lot of unnecessary work can be avoided.

> The seven abstraction layers of the OSI model can be defined as follows:

1. Application Layer
2. Presentation Layer
3. Session Layer
4. Transport Layer
5. Network Layer
6. DataLink Layer
7. Physical Layer

> In order for human-readable information to be transferred over a network from one device to another, the data must travel down the seven layers of the OSI model on the sending device and then travel up the seven layers on the receiving end.

### ❇Application Layer

<img alt="OSI Model" width="700px" src="/assets/images/osi-app.svg" />

* This is the only layer that directly interacts with data from the user.
* Software applications like web browsers and email clients rely on the application layer to initiate communications.
* Application layer protocols include **HTTP** as well as **SMTP**(Simple Mail Transfer Protocol is one of the protocols that enables email communications).

### ❇Presentation Layer

<img alt="OSI Model" width="700px" src="/assets/images/osi-pres.svg" />

* The presentation layer is responsible for translation, encryption, and compression of data.
* This layer is responsible for adding the encryption on the sender’s end as well as decoding the encryption on the receiver's end so that it can present the application layer with unencrypted, readable data.
* Presentation layer is responsible for compressing data it receives from the application layer before delivering it to Session layer. This helps improve the speed and efficiency of communication by minimizing the amount of data that will be transferred.

### ❇Session Layer

<img alt="OSI Model" width="700px" src="/assets/images/osi-sess.svg" />

* This is the layer responsible for opening and closing communication between the two devices.
* The time between when the communication is opened and closed is known as the session.
* The session layer also synchronizes data transfer with checkpoints.

?> For example, if a 100 megabyte file is being transferred, the session layer could set a checkpoint every 5 megabytes. In the case of a disconnect or a crash after 52 megabytes have been transferred, the session could be resumed from the last checkpoint, meaning only 50 more megabytes of data need to be transferred. Without the checkpoints, the entire transfer would have to begin again from scratch.

### ❇Transport Layer

<img alt="OSI Model" width="700px" src="/assets/images/osi-trans.svg" />

* This Layer is responsible for end-to-end communication between the two devices.
* Takes data from the session layer and breaking it up into chunks called **segments** before sending it to Network layer.
* The transport layer on the receiving device is responsible for reassembling the segments into data the session layer can consume.
* The transport layer is also responsible for flow control and error control.
* Flow control determines an optimal speed of transmission to ensure that a sender with a fast connection doesn’t overwhelm a receiver with a slow connection.
* The transport layer performs error control on the receiving end by ensuring that the data received is complete, and requesting a retransmission if it isn’t.

### ❇Network Layer

<img alt="OSI Model" width="700px" src="/assets/images/osi-net.svg" />

* The network layer is responsible for facilitating data transfer between two different networks.
* The network layer breaks up segments from the transport layer into smaller units, called **packets**, on the sender’s device, and reassembling these packets on the receiving device.
* The network layer finds the best physical path for the data to reach its destination; this is known as **routing**.

!> If the two devices communicating are on the same network, then the network layer is unnecessary.

### ❇DataLink Layer

<img alt="OSI Model" width="700px" src="/assets/images/osi-data.svg" />

* The data link layer is very similar to the network layer, except the data link layer facilitates data transfer between two devices on the SAME network.
* The data link layer takes packets from the network layer and breaks them into smaller pieces called **frames**.
* The data link layer is also responsible for **flow control and error control** in intra-network communication.

### ❇Physical Layer

<img alt="OSI Model" width="700px" src="/assets/images/osi-phy.svg" />

* This layer includes the physical equipment involved in the data transfer, such as the cables and switches.
* This is also the layer where the data gets converted into a bit stream.
* The physical layer of both devices must also agree on a signal convention so that the 1s can be distinguished from the 0s on both devices.

## ⚡Example

### ❇From Client End

?> **Mr. Cooper wants to send Ms. Palmer an email**. Mr. Cooper composes his message in an email application on his laptop and then hits ‘send’.

1. Cooper email application will pass his email message over to the **application layer**, which will pick a **protocol (SMTP)** and pass the data along to the presentation layer.
2. The **presentation layer** will then **compress the data** and then it will hit the session layer.
3. The **Session Layer** will initialize the **communication session**.
4. The data will then hit the sender’s **transportation layer** where it will be **segmented**.
5. Those segments will be broken up into **packets** at the **network layer**.
6. Which will be broken down even further into **frames** at the **data link layer**. The data link layer will then deliver those frames to the physical layer.
7. **Physical layer** will convert the data into a bitstream of **1s and 0s** and send it through a physical medium, such as a **cable**.

### ❇On Other End

?> Once Ms. Palmer’s computer receives the bit stream through a physical medium (such as her wifi), the data will flow through the same series of layers on her device, but in the opposite order.

1. First the **physical layer** will convert the bitstream from **1s and 0s into frames** that get passed to the data link layer.
2. The **data link layer** will then **reassemble the frames into packets** for the network layer.
3. The **network layer** will then **make segments out of the packets** for the transport layer, which will reassemble the segments into one piece of data.
4. The data will then flow into the receiver's **session layer**, which will pass the data along to the presentation layer.
5. The **presentation layer** will then **remove the compression** and pass the raw data up to the application layer.
6. The **application layer** will then feed the human-readable data along to email software.

> [🌐 Reference](https://www.lifewire.com/layers-of-the-osi-model-illustrated-818017)

> [🌐 Reference](https://www.cloudflare.com/learning/ddos/glossary/open-systems-interconnection-model-osi/)