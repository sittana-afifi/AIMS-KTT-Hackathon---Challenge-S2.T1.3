***1. Hour-by-Hour Timeline***
   **Hour 1**: Environment setup, data exploration of catalog.csv, and initial TF-IDF indexing:
                Analyzed the concept of Position Bias versus Intentional Relevance. I noted that in my data, a click at Rank 4 (33.3% CTR) is more statistically "valuable" than a click at Rank 1 (30.1% CTR). This is because the user had to bypass three other options to select that specific item, signaling a much stronger match for their intent.
                
   **Hour 2**: Implementation of the core recommender.py logic and the "local-boost" algorithm.
   **Hour 3**: Building the eval.ipynb to calculate NDCG@5 and local-presence rates; debugging code-switched query performance.
   **Hour 4**: Drafting dispatcher.md, recording the 4-minute video, and final README polish. 
***2. Key Technical Insights***
    *Understanding User Intent:*
        Rank 1 Clicks: Potentially "Lazy Clicks" due to position bias.
        Rank 3-4 Clicks: "High-Intent Clicks."

Decision: I will implement a Reciprocal Rank Weighting system. This gives higher "relevance credit" to products that win clicks despite being shown lower in the list. This is especially important for local Rwandan products that might start at lower ranks in a standard global baseline.
***3. LLM & Tool Declaration Tool***: [e.g., Claude 3.5 Sonnet].
   **Purpose**: [e.g., Generating the base TF-IDF class and troubleshooting pandas merge errors].
   **Sample Prompt 1**: [Paste your first actual prompt here].
   **Sample Prompt 2**: [Paste your second actual prompt here].
   **Sample Prompt 3**: [Paste your third actual prompt here].
   **Discarded Prompt**: [Paste a prompt that gave a bad result].
       *Why discarded*: [e.g., "The code it generated used a paid API which is prohibited by the technical constraints"].
***4. Hardest Decision Reflection***
    **First**: The most challenging part of the build was deciding how to reward products that were 'buried' but popular. I realized that a click on Rank 10 is more 'valuable' than a click on Rank 1 because it requires the user to actively seek out that product. To address this, I used Inverse Position Weighting. This logic ensures that if a 'Made in Rwanda' product is performing well at Rank 4, my system will 'promote' it to Rank 1, effectively using data-driven insights to boost local artisans.
    
    
