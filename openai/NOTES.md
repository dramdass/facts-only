# Notes
These are notes from Dennis Ramdass' experience with the OpenAI implementation and are to the best of his limited knowledge

* The difference between Custom GPTs and Assistants is not abundantly clear - it _seems_ that Custom GPTs are for non-coders and Assistants for coders
* Custom GPTs currently cannot be easily converted/extended to Assistants or vice-versa. They are both still in Beta so we don't know the convergence path
* Custom GPTs are not easily _exportable_ i.e., they cannot be saved in raw form, or through APIs, or source-controlled
* Assistants do not support _first-class exportability_ i.e. no export feature but available through RESTful APIs
* "File upload" is still more buggy and confusing that it needs to be:
  * It is only supported on the `code_interpreter` tool right now and not `retrieval` - unclear how that affects answers. I suspect newer models will support it.
  * I uploaded a `zip` file at create/configure type and it happily accepted it. At runtime when I tried a query, I received an error about invalid data source.
  * I then tried to upload a dataset of 9MB json file in create/configure - this complained it was too big.
  * I then had to split the 9MB json file into several smaller files of around 2MB and upload all of them.
  * I made a mistake with the splitting and again this wasn't caught at create/configure time.
  * It seems like there's a lot of low-hanging dataset validation that could be done.
  * When I fixed it, it worked well. As a plus, I was able to ask the GPT creation AI if it could correctly read my dataset and it confirmed.
* During create/configure, the GPT AI asked relevant me questions about tone of answers, which data sources to priortize and how to act with ambiguity.
  * These are what the industry considers to be "aligning" of LLM-based solutions to human preferences. It's clear OpenAI realizes the importance of alignment.
  * It would be really, really difficult or expensive to develop an _aligned_ chatbot quickly without this guidance. Prompt engineers are essentially doing alignment work.
 * CustomGPTs are great for non-engineers to build solutions but also for engineers to build, run, test, iterate fast cheap prototypes with no-code/low-code.
 * The nascent ecosystem for custom GPTs currently seem more like Chrome plugins than full-fledged apps.
 * There are likely to be millions of community GPTs and it's unclear what/how the "best" GPTs are going to be and how they are highlighted etc.
 * It is very important to note that by default, sharing of conversation data is **on** - I suspect OpenAI views this as a massive community data source.
 * Custom GPTs Pricing thus far:
   * Basic: ChatGPT plus subscriptions allow free creation and sharing with no clear monetization path for creator (yet?) with usage limits
   * Enterprise: No usage limits and more support
* I think _Assistants_ are the construct application developers will use and where more business value can be unlocked. 
* You really can't use _Assistants_ without billing setup and the pricing is simple but total cost to owner is difficult to guess without usage
* Create/configure is noticably slow i.e. configure button hangs spinning for some time
* The chatbot is very slow compared to native ChatGPT. There could be a few reasons for this with any number of them being true:
  * These features are in Beta and may improve
  * It could be a one-time cold-start thing
  * It could be because I instructed it to heavily use the provided dataset for an authoritative source of truth
  * I need to pay more to OpenAI for performant inference
  * **Update:** Most likely it is related to the reported current massive spike in usage of Open AI 
* Anecdotally with my interactions so far, it does a great job of being clear of what it does and doesn't know in the initial answer.
* Additional questioning usually holds up well e.g. "Who is your source?"
* The "alignment" instructions for a solution is critical - it's unclear to me how one would/should safely:
  * Version control them
  * Append/edit in a structured way
  * A/B test changes to the instructions
  * ... 
