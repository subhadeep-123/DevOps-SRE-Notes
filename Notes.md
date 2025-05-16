# Prometheus

## Observability

Observability is the ability to understand and measure the internal state of a system based on the data it generates. It enables you to derive actionable insights from unexpected behaviors in dynamic environments.

---

### Purpose

The primary goal of observability is to gain a deep understanding of the internal workings of a system.

---

### Troubleshooting with Observability

Effective troubleshooting goes beyond identifying *what* went wrong. It helps answer:

* **Why** did the application enter a specific state?
* **What** component is responsible?
* **How** can we prevent it in the future?

---

### Fundamentals of Observability

#### The Three Pillars of Observability

1. **Logging**
2. **Metrics**
3. **Tracing**

---

#### Logs

Logs are time-stamped records of discrete events within a system.

**Logs typically include:**

* A **timestamp** indicating when the event occurred.
* A **message** describing the event.

Logs from concurrent systems can be interleaved and distributed across different components.

---

#### Traces

Traces help follow a request as it traverses through various services, providing a holistic view of its journey—hop by hop.

**Components of a trace:**

* **Trace ID**: Identifies the entire request lifecycle.
* **Spans**: Individual units of work within the trace.

Each **span** includes:

* **Start time**
* **Duration**
* **Parent Span ID**

> ![Traces](./img/traces.png)

---

#### Metrics

Metrics represent quantitative data points that reflect the system’s state.

**Examples:**

* CPU load
* Number of open files
* HTTP response times
* Error rates

Metrics are often visualized over time to uncover trends and anomalies.

**A metric consists of:**

1. **Metric Name**
2. **Value** (current or recent)
3. **Timestamp**
4. **Dimensions** (contextual metadata)

---

### SLO / SLA / SLI Explained

#### SLI (Service Level Indicator)

A quantifiable measure of service performance.

**Examples:**

* Request latency
* Error rate
* Throughput
* Availability
* Resource saturation

> Not all metrics make good SLIs; the focus should be on those that reflect **user experience**.

---

#### SLO (Service Level Objective)

A target or acceptable range for an SLI. It is a promise about the expected performance level.

**Examples:**

* **Latency SLO**: Response time < 100 ms
* **Availability SLO**: 99.9% uptime

> SLOs are defined from the **customer’s perspective**.

---

#### SLA (Service Level Agreement)

A formal agreement between a service provider and a user that enforces a specific SLO.

* May include **financial** or **contractual** consequences if targets are not met.

---

## Prometheus Fundamentals

1. **Prometheus** is an open-source monitoring system for collecting and querying metrics data.
2. It supports **alerting** based on metric thresholds.
3. Prometheus **scrapes** metrics from configured targets via an HTTP endpoint.
4. Scraped data is stored in a **time-series database** and queried using **PromQL** (Prometheus Query Language).
