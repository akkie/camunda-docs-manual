---

title: 'JTA Transaction Integration'
weight: 20

menu:
  main:
    identifier: "user-guide-cdi-transactions"
    parent: "user-guide-cdi"

---

The process engine transaction management can integrate with JTA. In order to use JTA transaction
manager integration, you need to use the

* `org.camunda.bpm.engine.impl.cfg.JtaProcessEngineConfiguration` for JTA Integration only
* `org.camunda.bpm.engine.cdi.CdiJtaProcessEngineConfiguration` for additional CDI Expression
  resolving support.

> **Note 1**: The shared process engine distributions for Java EE Application Servers (Wildfly, JBoss,
>  IBM WebSphere Application Server, Oracle WebLogic Application Server) provide JTA
> integration out of the box.

> **Note 2**: The process engine requires access to an implementation of
> `javax.transaction.TransactionManager`. Not all application servers provide such an
> implementation. Most notably, IBM WebSphere and Oracle WebLogic historically did not provide this
> implementation. In order to achieve JTA Transaction Integration on these containers, users should
> use the Spring Framework Abstraction and configure the process engine using the
> [SpringProcessEngineConfiguration]({{< relref "user-guide/spring-framework-integration/index.md">}}).
