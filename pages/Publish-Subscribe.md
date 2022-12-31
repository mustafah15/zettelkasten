---
title: Publish-Subscribe
---

- Publish-Subscribe
id:: 1fef11e1-e4d1-45d4-8c65-ea8b97419ab5
	 - In the pub-sub (short for publish-subscribe) model, messages are divided into topics. A publisher (or a producer) sends a message to a topic that gets stored in the messaging system under that topic. Subscribers (or the consumer) subscribe to a topic to receive every message published to that topic. Unlike the Queuing model, the pub-sub model allows multiple consumers to get the same message; if two consumers subscribe to the same topic, they will receive all messages published to that topic.
id:: 6354b380-6935-447a-a3d7-b39c5db9cc68

	 - The messaging system that stores and maintains the messages is commonly known as the message **broker**. It provides a loose coupling between publishers and subscribers, or producers and consumers of data.
id:: 8cf9ee9a-8f44-4af5-8ed2-9c9e38787159

	 - The message broker stores published messages in a queue, and subscribers read them from the queue. Hence, subscribers and publishers do not have to be synchronized. This **loose coupling** enables subscribers and publishers to read and write messages at different rates.
id:: a1ae5030-61f8-4065-8297-785598876725

	 - The messaging system’s ability to store messages provides **fault-tolerance**, so messages do not get lost between the time they are produced and the time they are consumed.
id:: d8cd65f0-6e0b-41b5-988d-f9aead8b41ca

	 - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Fsoftware-architecture%2FcHy74FaNj_.png?alt=media&token=99410565-e700-4cc1-9fd2-59000719455e)
id:: 875fc146-8841-41b6-a883-57b6ec015320
