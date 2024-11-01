# A Technical Study of Algorithmic Bias on X

This repository contains Python code and data collection instructions for a technical report: "A computational analysis of potential algorithmic bias on platform X during the 2024 US election" (Graham &amp; Andrejevic, 2024). 

To reproduce this analysis, two steps are required. 

1. Data collection

The [post IDs are available in this repository](https://github.com/timothyjgraham/AlgorithmicBiasX/blob/main/tweet_ids.csv) for those who have access to the X API and can collect them via that source.

As the API access is expensive, the other way to collect the data is via scraping. I recommend using the open source toolkit Zeeschuimer, which is what we used in the report.
Data collection using Zeeschuimer involves collecting posts by using the web search on X and scrolling through the posts. To make this easier we recommend using the FoxScroller plugin, which automatically scrolls for you at a fixed rate of pixels per second. A rate of 1100 px/s seems to be a good balance between speed and avoiding glitches with the browser loading content in the DOM. 

There is a limitation with platform X where it has a limit to how far you can scroll back on a profile's timeline. I found a way to get around this by using the X advanced search. Once you hit the limit you can use an advanced search query of this pattern: (from:elonmusk until:YYYY-MM-DD), where the date is the point at which you previously got cut off. This enables loading posts from earlier in the timeline. It’s laborious but it works.

<p>
  <img src="https://github.com/timothyjgraham/AlgorithmicBiasX/blob/main/Unknown-15.png" alt="Elon Musk's view count over time showing evidence of algorithmic amplification" align="right" width="500" style="margin-left: 15px;">
  
2. Statistical analysis in Python

The Zeeschuimer tool produces data in NDJSON format. To be honest, it's a bit tricky to process this data due to the complex structure. The Python code handles all this by fetching the relevant fields from the JSON structure. So you just need to ensure the NDJSON file containing your data is in the same working directory as the code, or otherwise change the file path in the code itself.

The code produces all the outputs in the report, including the diagrams. It is labelled with headings for clarity. [Download the code or view it directly on Google Colab](https://github.com/timothyjgraham/AlgorithmicBiasX/blob/main/Code_for_report_A_computational_analysis_of_potential_algorithmic_bias_on_platform_X_during_the_2024_US_election.ipynb)

If you have any questions please post as an Issue on this repository or contact Timothy Graham (QUT).

</p>
