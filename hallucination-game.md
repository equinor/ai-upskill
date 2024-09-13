# The Hallucination Game

This is a good introduction to chat AIs, for example to chat.equinor.com or some other app. Note that different models and different model versions will react differently to these questions, but in general you should be able tofind some questions that reliably lead to hallucinations.


## Script

Let's ask a question: "Tell me about Equinor." The answer is quite reasonable. The eloquence and information content of the answer is impressive. There is no doubt that this technology is remarkable.

I have a follow-up question, "Why did Statoil get out of the whale oil business in 1987?". The model will almost always reply with a completely made up story (Statoil was never in the whale oil business), revealing an error mode called **hallucination**. The justification can be quite elaborate. As usual, it is eloquent and very believable. But if you ask "When did Statoil get out of the whale oil business?", the model usually responds correctly because the question is less leading. Asking, "Was Statoil ever in the whale oil business?" will nearly always get a correct response.

Here's a challenge for you: see if you can get the model to hallucainte something about Equinor or about your home town.

_Allow about 5 to 10 minutes for people to explore on their own or in pairs. Walk around checking that people are able to get into it._

## Follow up

_Ask for volunteers to share any especially surprising or funny hallucinations._

In my experience, the model tends to hallucinate when asked leading questions about things that are not true, or misleading questions about things that are. 

For example, "In which Tintin story does he sell his fossil collection?" tends to lead to a hallucination (ask, "and why?" if it doesn't give a hallucinated reason). It sounds plausible. But if you change "fossil" to "DVD", the model usually groks that this is anachronistic and correctly challenges the storyline.

Here are some others:

- `Can I drink molten ice?` (that is, water)
- `Why is Mercury the closest planet to Jupiter, on average?` (this is true for all of the planets)
- `What are Equinor's brand colours?`
- `Why did Buzz Aldrin bring a Buzz Lightyear toy on Apollo 11?`
- `Tell me something amazing about the recreational facilities on the Stavanger Field platform.`
  
