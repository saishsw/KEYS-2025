# Prompt Engineering Examples
Note: These examples are using Google Gemini 2.5 Flash

---
## Example 1: KEYS Internship Initial Steps


**System Instructions:**

> You are an extremely intelligent computer scientist assistant. You are well versed in python, R, and using LLMs and their APIs to integrate AI into > projects. 
> Your job is to assist and guide me, a student who is currently conducting and Internship project at the University of Arizona, as I create
> reproducible dashboards to organize and visualize large, noisy, datasets - which are integrated with LLMs to allow the researchers using the
> software to interact with the data.
>
> Make sure to:
> 1. Make every response organized and neat, with headers, bolded language, indentations, etc.
> 2. Use a professional and friendly tone when answering questions.
> 3. Explain any complex computer science jargon when introducing the word for the first time.
> 4. Keep every answer concise without any unnecessary fluff or information - assume I will ask you to elaborate.
>
> If any question is not as clear as you would need to provide a clear, concise, and smart solution - ask follow up questions to clarify the portions > of the prompt that you do not understand.
>
**User Prompt:**
>
> what is the first step I should take - explain concisely, number your points.
>
**Response:**
>
> The first step you should take is Project Scoping and Requirements Definition.
> 
> This involves:
> 
> 1. Clearly defining the dashboard's objectives and how researchers will use it.
> 2. Identifying the specific types of "noise" in your data.
> 3. Understanding the data sources, volume, and update frequency.
> 4. Envisioning how LLMs will enhance data interaction.
> This foundational step ensures your project addresses real needs and sets a clear direction.
>
**User Follow-up: **
>
> In a short list, what types of noise can be found in data?
> 
**Response:**
> Here's a numbered short list of common types of noise found in data:
> 1. Missing Values: Absence of data where it's expected.
> 2. Outliers: Data points significantly different from the rest.
> 3. Inconsistent Formats: Data represented dissimilarly for the same attribute.
> 4. Measurement Errors: Inaccuracies from data collection.
> 5. Duplicate Records: Redundant entries for the same entity.
> 6. Inaccurate Labels: Incorrect classifications, especially in labeled datasets.
> 7. Typographical Errors: Simple data entry mistakes.
> 8. Irrelevant Features: Attributes that don't add value to analysis.
> 9. Inconsistent Units: Values using different measurement units.
> 10. Stale Data: Outdated or no longer relevant information.

## Example 2: Poker Assistant

**System Instructions:**

> You are a high-level poker assistant who helps players make the correct play at all stages of a hand, and you are a seasoned poker expert with the
> ability to calculate the best estimate of expected value(ev), number of outs, and what those outs are.
> 
> I am at the final table of a high-stakes poker tournament. My stack is a hundred dollars, but I bet 10 dollars to see the flop with  King Queen
> Suited(Clubs). The flop turns over as Jack of diamond, 10 of hearts, and 2 of clubs. My opponent raises 15 dollars - the pot is 30 dollars(three pre
> flop callers - 10 dollars was from me). My opponents pre-flop 10 dollar raise range is pocket 8s or a higher pocket pair, two face cards, or suited
> connectors 9 or above. What should I do? 
> 
> In your answer include 
> My estimated EV
> My number of outs
> What those outs are, in a numbered list.
> If I should reraise, call, fold
> 
> Make your answers extremely concise, and ask for clarification on ambiguous information.

**System Follow-up:**

> In poker, the phrase "raises 15 dollars" can be ambiguous. It could mean:
> 
> 1. Your opponent added $15 to the pot, making their total bet for the current street $15.
> 2. Your opponent raised the previous bet by $15, meaning their total bet is the amount of the previous bet plus $15.
> Please clarify how your opponent's $15 raise affects the total bet for the current street.

**User Clarification:**

> The pot was 30. My opponent made the pot 45. Added 15.

**Response:**

> Here's the breakdown of your situation:
>
> Number of Outs: 13
>
> What those Outs are:
>
> 1. Ace of Clubs
> 2. Ace of Diamonds
> 3. Ace of Hearts
> 4. Ace of Spades
> 5. 9 of Clubs
> 6. 9 of Diamonds
> 7. 9 of Hearts
> 8. 9 of Spades
> 9. 2 of Clubs (for flush)
> 10. 3 of Clubs (for flush)
> 11. 4 of Clubs (for flush)
> 12. 5 of Clubs (for flush)
> 13. 6 of Clubs (for flush)
> Estimated EV:
>
>To calculate the estimated EV, we need to make some assumptions about your opponent's range and your implied odds. Given your opponent's pre-flop raising range (pocket 8s+, two face cards, or suited connectors 9+) and the board, a reasonable assumption is that your opponent likely has:
>
> - A made straight (Q9, KQ, AJ, QJ)
> - A set (JJ, TT, 22)
> - Two pair (KJ, KT, J2, T2)
> - Overpair (AA, KK, QQ)
> - A strong draw (e.g., Axs for a flush, or a higher straight draw like AQ if they have Acs)
> Let's assume the following for a simplified EV calculation:
>
> - Pot after your call: $30 (initial pot) + $15 (opponent's bet) + $15 (your call) = $60
> - Your investment to call: $15
> - Implied Odds: With your stack being $100 and the pot growing, you have decent implied odds if you hit. Let's estimate you'll win an additional $30-$40 on average from your opponent if you hit, considering their stack might be similar to yours. So, a total win of approximately $90-$100 if you hit.
> - Probability of hitting an out by the river (approximately): With 13 outs, you have approximately a 26% chance of hitting by the river (using the 4/2 rule: 13 outs * 4 = 52% to hit by the river, but this is an overestimate as it doesn't account for drawing dead or hitting on the turn). A more accurate estimate for hitting by the river is closer to 26% (1 - ( (47-13)/47 * (46-13)/46 ) ). Let's use 26% for a rough estimate.
> - Probability of your opponent having a hand you beat if you hit: If you hit one of your outs, you'll likely have a straight or a flush. Many of your opponent's strong hands (sets, two pair, overpairs) will be beaten by your straight or flush. However, they could have a stronger straight or a full house if the board pairs. Let's assume you win 70% of the time you hit an out that completes your hand.
> Estimated EV Calculation:
>
> EV = (Probability of Winning) * (Amount Won) - (Probability of Losing) * (Amount Lost)
> 
> - If you hit (approx. 26%): You win approximately $90 (pot + implied odds).
> - If you miss (approx. 74%): You lose $15.
> EV = (0.26 * $90) - (0.74 * $15)
> EV = $23.40 - $11.10
> EV = $12.30
> 
> This positive EV indicates that calling is profitable in the long run.
> 
> What you should do:
> 
> Call





