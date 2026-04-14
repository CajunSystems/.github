# 🌶️ Welcome to CajunSystems

**Modern Java concurrency and effects, simplified.**

CajunSystems is building the next generation of concurrency and functional programming tools for Java. We leverage the power of Java 21+ virtual threads and modern JVM features to make concurrent and functional programming accessible, performant, and enjoyable.

## 🚀 Our Projects

### [Cajun](https://github.com/CajunSystems/cajun) - Actor System for Java

A lightweight actor system that brings predictable, safe concurrency to Java applications through message-passing instead of locks.

**What makes Cajun special:**
- 🎭 **Message-based concurrency** - No more fighting with locks and shared state
- ⚡ **Virtual thread powered** - Built for Java 21+ with exceptional performance (0.02% overhead for I/O workloads)
- 🏗️ **Battle-tested patterns** - Actor hierarchies, supervision strategies, and backpressure management
- 💾 **Production-ready persistence** - LMDB support for stateful actors
- 🌐 **Distributed by default** - Cluster mode for scaling across nodes

**Perfect for:** Microservices, event-driven systems, stateful services, and message-driven architectures

```java
// Simple actor example
Pid actorPid = system.actorOf(GreetingHandler.class)
    .withId("greeter-1")  // Optional: specify ID (otherwise auto-generated)
    .spawn();

actorPid.tell(new HelloMessage());
```

[→ Explore Cajun](https://github.com/CajunSystems/cajun)

---

### [Roux](https://github.com/CajunSystems/roux) - Effects Library for Java

A lightweight effects system that makes functional programming in Java feel natural and powerful.

**What makes Roux special:**
- 🧵 **Virtual thread native** - Designed from the ground up for structured concurrency
- 🔧 **Pragmatic functional programming** - Stays close to Java's idioms while adding power
- 🎯 **Type-safe error handling** - Explicit error channel with `Effect<E, A>`
- 🔀 **Composable by design** - Rich combinators like `map`, `flatMap`, `catchAll`, and more
- ⚙️ **Flexible execution** - Pluggable runtimes with async support and cancellation

**Perfect for:** Clean error handling, composable async operations, and functional architectures

```java
// Composing effects
Effect<IOException, String> readConfig =
    Effect.of(() -> Files.readString(path))
          .map(String::trim)
          .catchAll(err -> Effect.success("default-config"));
```

[→ Explore Roux](https://github.com/CajunSystems/roux)

---

### [Gumbo](https://github.com/CajunSystems/gumbo) - Shared Log & Executor Framework

The foundational layer powering the newer CajunSystems projects. Gumbo provides a shared structured log and virtual-thread executor for the JDK 21+.

**What makes Gumbo special:**
- 📋 **Structured shared log** - Consistent, queryable log infrastructure across services
- ⚡ **Virtual-thread executor** - High-throughput execution built for Java 21+
- 🧱 **Foundation for the ecosystem** - The building block that Bayou and Boudin build upon

[→ Explore Gumbo](https://github.com/CajunSystems/gumbo)

---

### [Bayou](https://github.com/CajunSystems/bayou) - Actor System on Gumbo

An actor system built on top of Gumbo, inheriting its structured log and executor for a lightweight, performant concurrency model.

**What makes Bayou special:**
- 🎭 **Actor-based concurrency** - Message-passing model on Gumbo's virtual-thread executor
- 📋 **Gumbo-powered logging** - Actors emit structured logs through the shared Gumbo log
- 🔗 **Ecosystem integration** - Works seamlessly alongside Boudin workflows

[→ Explore Bayou](https://github.com/CajunSystems/bayou)

---

### [Boudin](https://github.com/CajunSystems/boudin) - Workflow System on Gumbo

A workflow system built on top of Gumbo, enabling composable, durable pipelines driven by Gumbo's execution model.

**What makes Boudin special:**
- 🔄 **Composable workflows** - Chain steps into durable, inspectable pipelines
- ⚙️ **Gumbo-powered execution** - Workflows run on Gumbo's virtual-thread executor
- 📋 **Structured observability** - Workflow state flows through the shared Gumbo log

[→ Explore Boudin](https://github.com/CajunSystems/boudin)

---

## 🤝 Join the Community

We believe great software is built by passionate communities. Whether you're fixing a typo, implementing a feature, or sharing an idea, **your contributions are welcome!**

### Ways to Contribute

- 🐛 **Report bugs** - Found something broken? Open an issue
- 💡 **Suggest features** - Have an idea? We'd love to hear it
- 📖 **Improve docs** - Documentation is never perfect
- 🔨 **Submit PRs** - Code contributions are always appreciated
- 💬 **Join discussions** - Share your experiences and help others

### Getting Started

1. **Check out the repositories** - Browse [Cajun](https://github.com/CajunSystems/cajun), [Roux](https://github.com/CajunSystems/roux), [Gumbo](https://github.com/CajunSystems/gumbo), [Bayou](https://github.com/CajunSystems/bayou), and [Boudin](https://github.com/CajunSystems/boudin)
2. **Look for "good first issue" labels** - Perfect for getting familiar with the codebase
3. **Read the contribution guidelines** - Each project has guidelines in its repository
4. **Join the conversation** - Participate in issues and discussions

### Requirements

All projects require **Java 21+** to take advantage of modern JVM features like virtual threads and structured concurrency.

---

## 🌟 Why CajunSystems?

Modern Java has incredible capabilities, but concurrent and functional programming shouldn't require a PhD to use effectively. We're building tools that:

- ✅ Embrace modern Java features (virtual threads, structured concurrency)
- ✅ Provide exceptional performance with minimal overhead
- ✅ Stay pragmatic and close to Java's idioms
- ✅ Scale from simple applications to distributed systems
- ✅ Make complex patterns accessible to all developers

---

## 📦 Installation

**Cajun** and **Roux** are available on Maven Central:

**Cajun:**
```xml
<dependency>
    <groupId>systems.cajun</groupId>
    <artifactId>cajun</artifactId>
    <version>0.7.0</version>
</dependency>
```

**Roux:**
```xml
<dependency>
    <groupId>systems.cajun</groupId>
    <artifactId>roux</artifactId>
    <version>0.2.2</version>
</dependency>
```

**Gumbo**, **Bayou**, and **Boudin** are available via [JitPack](https://jitpack.io). Add the JitPack repository first:

```xml
<repositories>
    <repository>
        <id>jitpack.io</id>
        <url>https://jitpack.io</url>
    </repository>
</repositories>
```

Then add the dependencies:

**Gumbo:**
```xml
<dependency>
    <groupId>com.github.CajunSystems</groupId>
    <artifactId>gumbo</artifactId>
    <version><!-- check latest version on JitPack --></version>
</dependency>
```

**Bayou:**
```xml
<dependency>
    <groupId>com.github.CajunSystems</groupId>
    <artifactId>bayou</artifactId>
    <version><!-- check latest version on JitPack --></version>
</dependency>
```

**Boudin:**
```xml
<dependency>
    <groupId>com.github.CajunSystems</groupId>
    <artifactId>boudin</artifactId>
    <version><!-- check latest version on JitPack --></version>
</dependency>
```

---

## 📬 Get in Touch

Have questions? Want to discuss architecture decisions? Need help getting started?

- Open an issue in the respective repository
- Start a discussion on GitHub
- Check out existing issues and PRs

We're here to help and excited to see what you build!

---

**Happy coding! 🌶️**
