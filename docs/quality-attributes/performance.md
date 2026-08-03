# Performance

## Definition

Performance describes how efficiently a system responds to requests and processes workload.

It should not be evaluated using only one metric.

---

## Main Metrics

### Response Time

Response time is the total time between sending a request and receiving the complete response.

Example:

- Average response time: 180 ms

An average of 180 ms means that some requests may be faster and others may take longer.

---

### Latency

Latency represents the delay experienced before the system begins returning a response.

It can be affected by:

- Network delay
- Distance between client and server
- Queueing
- External service calls
- Infrastructure overhead

Latency is one component that can influence the total response time.

---

### Throughput

Throughput measures how much work a system can process within a period of time.

Example:

- 1,500 requests per second

This means that the system can process approximately 1,500 requests every second under the measured conditions.

---

## Important Distinction

- Response time measures how long one request takes.
- Throughput measures how many requests the system can process.
- Latency measures delay.

A system can have:

- Low response time but low throughput
- Higher response time but very high throughput

Therefore, it is not possible to say that one system has better performance without understanding the business requirements.

---

## Example

### System A

- Response time: 50 ms
- Throughput: 100 requests per second

### System B

- Response time: 300 ms
- Throughput: 20,000 requests per second

System A may be more appropriate when very low response time is critical.

System B may be more appropriate when the system must process a very large number of requests.

The correct choice depends on the architectural drivers.

---

## Investigating a Slow API

Before changing the code, relevant questions include:

- Is the problem constant or does it happen only during peak periods?
- What is the average response time?
- What are the p95 and p99 response times?
- How many requests per second is the API receiving?
- Is the database query slow?
- Are database indexes missing?
- Is the API returning more data than necessary?
- Are external services being called?
- Is CPU or memory usage high?
- Is the request waiting in a queue?
- Does the problem happen in every environment?

---

## Key Takeaways

- Performance is broader than speed.
- Average response time alone is not enough.
- Throughput and latency must also be considered.
- Performance requirements must be measurable.
- Optimisation should start with measurement, not assumptions.
- The expected workload determines what good performance means.