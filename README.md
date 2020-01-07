
SaGe is a SPARQL query engine for public knowledge graph that implements [Web preemption](#preemption). Thanks to web preemption, Sage ensures that any SPARQL query delivers complete results ie. Sparql queries cannot be interrupted after a quota of time fixed by knowledge graph provider. 

The complete approach and experimental results are available in a Research paper accepted at The Web Conference 2019. Thomas Minier, Hala Skaf-Molli and Pascal Molli. ["SaGe: Web Preemption for Public SPARQL Query services"](https://hal.archives-ouvertes.fr/hal-02017155/document) in Proceedings of the 2019 World Wide Web Conference (WWW'19), San Francisco, USA, May 13-17, 2019. [(slides)](https://docs.google.com/presentation/d/1zSMKwTq6N6IJFs4jFkOqRzpfooDDoLGhR-3yYRUSij8/present?slide=id.p)

An online demonstration is available at [sage.univ-nantes.fr](http://sage.univ-nantes.fr)



## <a name="preemption"></a>What is web preemption?

Web preemption is the capacity of a Web server to suspend a running query after a fixed quantum of time and resume the
next waiting query. Web preemption is similar to time-sharing in operating systems where the web server plays the role of the CPU and web request plays the role of processes.

![web preemption states](state.png)

### SaGe general architecture

The SPARQL engine includes a smart Sage client and a Sage SPARQL query server hosting RDF datasets as depicted in the figure below:
![smart client](lcls.png)

Preemptable sparql operators are natively implemented in the server. Non-preemptable sparql operators are processed in the smart client.

We provide 2 implementations of the smart client:
* one in Java as an extension of JENA, we call it [sage-jena](https://github.com/sage-org/sage-jena). 
* one in pure javascript, we call it [sage-client](https://github.com/sage-org/sage-client).

The server itself is written in python and we call it [(sage-engine)](https://github.com/sage-org/sage-engine)

### Contact


