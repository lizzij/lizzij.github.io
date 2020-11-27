---
layout: post
comments: true
title: "Mastering TCP/IP"
date: 2020-11-26 12:00:00
tags: network
---


> I am ploughing through the book《图解 TCP/IP》or *Mastering TCP／IP* - a book written by Takafumi Takeshita et al. (in Japanese), translated into Chinese, and I am taking notes in English.


<!--more-->



《图解 TCP/IP》or *Mastering TCP／IP* seems to be a widely popular intro level textbook to computer networks in Asia. It has more visual illustrations and metaphors compared to other textbooks like *Computer Networking: A Top-Down Approach*. When it was published in 1994, the Internet and TCP/IP were not as commonplace as they are today.

All in all, it is great intro read to intuitively understand how the computer networks work and how they have evolved over the years.

Progress: &nbsp;&nbsp;<progress id="file" max="309" value="50"></progress>&nbsp;&nbsp;50/309 pages

{: class="table-of-content"}
* TOC
{:toc}



## Intro to Computer Networks
To simply put, computer networks exist to connect computers. There are essentially 7 stages in the history of computers and networks:
1. **Batch processing** - Back in the days, computers can only run one program at a time. People use batches of punch cards or magnetic tapes to load program and get output.
2. **Time sharing system (TSS)** - Again back in the days, computers were expensive. TSS allows multiple users to share computing resources simultaneously.
3. **Communication between computers** - Still back in the days, transferring data between computers means moving physical magnetic tapes and soft drives. With inter-computer communication, programming becomes distributed.
4. **Computer networks emerge** - In the 80s, new networks allow various types of computer to connect.
5. **The Internet** - in the 90s, personal computer becomes prevalent resulting in a need to connect more computers.
6. **Internet Protocol (IP)** - Infrastructural ethernet gradually replaced by the Internet Protocol. Internet of things connect more than computers to the networks.
7. **Security** - There is a shift of focus from functionality to security.

### Protocol

#### What is a protocol?
Different computers (with different CPU and OS) needs to abide to the same set of "rules" in order to communicate via computer networks. In some way, a protocol is like a natural language: When two people both speak Chinese (protocol), they can chat (communication) and exchange information (data). Similarly, two computers can abide to same TCP/IP.

When we mail a letter, we write down the sender and received information on the envelope. Similarly, computers state those information in the **header**. Larger data is sliced into smaller **packets** and will be reassembled at the receiver. Computer agree on how to slice and reassemble the packets according to the protocol.

#### Who decides the protocol?
Initially, every computer manufacture came up with their own protocol; and not surprisingly, it was hard establish networks (it's like everyone is speaking their dialect thus unable to communicate effectively). To solve the issue, ISO (International Organization for Standards) established an international **OSI** (Open Systems Interconnection). It was later often adapted and used in network protocols.

TCP/IP was not established by ISO. It was popularized by IETF (Internet Engineering Task Force) and have became the industry standard.

#### What's in a protocol?
ISO decided on a **7-layer** OSI model. Each intermediate layer serves a class of functionality to the layer above it and is served by the layer below it. Two standards are defined for each layer: one specifies the **interface** to the services used by the player above/below, and the other specifies the **protocol** used by a corresponding layer.

![Layer Metaphor]({{'/assets/images/2020-11-26-mastering-tcp-ip/layer-metaphor.png'|relative_url}}){: style="width: 36%;" class="center"} *Fig. 1. intuitively understand layers, interface and protocol. (Image source: replotted based on an image from Takeshita et al., 2010).*

Metaphorically, imagine two people talking on the phone in Chinese. There are two layers: language layer and device layer. The language layer protocol is Chinese, and the device layer protocol is however the phone exchanges data. The interface between human and the device is the mic. They may decide to switch to Korean (change language layer protocol), or switch to using walky-talky (change device layer protocol).

![Layer Communication]({{'/assets/images/2020-11-26-mastering-tcp-ip/layer-communication.png'|relative_url}}){: style="width: 50%;" class="center"} *Fig. 2. How layers communicate in the case of sending an email. (Image source: replotted based on an image from Takeshita et al., 2010).*

The following table specifies the protocol data unit and functionality of each layer:

{: class="info"}
|  | Layer | Protocol Data Unit | Function |
| --- | --- | --- | --- |
| 7 | Application | Data | High-level APIs |
| 6 | Presentation | Data | Translation of data between a networking service and an application |
| 5 | Session | Data | Managing communication sessions |
| 4 | Transport | Segment, Datagram | Reliable transmission of data segments between points on a network |
| 3 | Network | Packet | Structuring and managing a multi-node network |
| 2 | Data link | Frame | Reliable transmission of data frames between two nodes connected by a physical layer |
| 1 | Physical | Bit, Symbol | Transmission and reception of raw bit streams over a physical medium |

#### Key concepts in computer networks
**Connection-oriented** service establish connection before sending data. **Connectionless** service sends data anytime. **Circuit switching** requires one wire per connection (impossible). **Packet switching** uses a shared wire. Sending host breaks data into packets which are temporarily stored on routers, then forwarded to target receiving host (thus packet switching is also called store and forward). **Unicast** is 1:1, **broadcast** 1:all, **multicast** 1:many, **anycast** 1:any one.

Sending and receiving entities are identified by **address**. Addresses are unique and hierarchical. MAC address, IP address and port number are used in TCP/IP.

Computer networks are networks of computers connected via various types of wire or electromagnetic wave. Each has a different **bandwidth**, which uses Bits Per Second (bps) as unit.

![Network elements]({{'/assets/images/2020-11-26-mastering-tcp-ip/network-elements.png'|relative_url}}){: style="width: 100%;" class="center"} *Fig. 3. Elements of a computer network (Image source: based on an image from Takeshita et al., 2010).*

---
Cited as:
```
@article{huang2020mti,
  title   = "Mastering TCP/IP",
  author  = "Huang, Eliza",
  journal = "lizzij.github.io",
  year    = "2020",
  url     = "https://lizzij.github.io/2020/11/26/mastering-tcp-ip.html"
}
```



## Appendix
router 路由器
host 主机
connection-oriented service 面向有连接型服务
packet switching 分组交换
circuit switching 电路交换
switch 交换机


## References

[1] Takafumi Takeshita et al.. ["Mastering TCP/IP"](worldcat.org/title/tcpip-zong-he-ji-chu-pian/oclc/54668777) 2010.

[2] Oracle. ["Network Interface Guide"](https://docs.oracle.com/cd/E19455-01/806-1017/intro-4/index.html) 2010.
