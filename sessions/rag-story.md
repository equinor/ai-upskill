# RAG story

This short session uses the reduction of risk to motivate RAG, introduce the method, then explore its weaknesses. In other words, the story does not necessarily have a happy ending. <sad trombone>

You can probably pull off a really short session in 40 minutes, but you could easily use 2 hours if you have an actual RAG solution in hand and you develop some of these components.

- **Introduction** — thank host, introduce self, etc.
- **Poll** — if there's time, get to know the audience a bit, eg how often do they use chatbots at work, are they using custom (probably RAG) solutions already in their domain?
- **Disambiguate** — quick description of discriminative vs generative AI and remind people that ML is awesome
- **Chatbots**
  — Introduce a chatbot, eg Equinor Chat or ChatGPT. Start with something the chatbot does well...
  - ...then see issues (slight or harmless hallucination)...
  - ...then see major issues (outright extrapolation).
- **RAG!** — so we try retrieval augmented generation, definitely sounds like it should work. Draw an architecture diagram, preferably on a whiteboard or iPad, if you can pull it off in the time available. If possible, show a RAG solution in action. Show how it tries to ground its answers in retrieved documents. 
- **But!** — Point out that we (sort of) solved a problem, but now we have 10 new problems in the form of a bunch of hyperparameters: relevant docs, chunking, retrieval, prompting, etc. Hence we have a bunch of new ways for the chatbot to fail: misinterpreted instructions, malformed retrieval (eg querying an API or generating SQL), low relevance docs, poor summarization, etc.
- **Testing and red teaming** — So teams need ways to evaluate performance! And we need testing. The user/customer must help design all these tests to try to ensure that the solution meets their needs. It's going to take time, but it's totally necessary if we aren't going to deploy broken technology into safety critical situations.
- **Discussion** — if there's time, ask people what they think. If at all possible, get them talking to each other and provoke them with a question, preferably about their domain.
- **Next steps, resources, thanks and bye**
