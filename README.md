# Purpose

This repository contains some of Judicata's case search benchmark data. We're
open-sourcing it to give the legal tech industry a common measuring stick for
evaluating search performance. See [this post](https://blog.judicata.com/legal-search-sharing-judicatas-data-to-drive-progress-811eed64f04b)
for more of our motivation.

# Contents

The repository contains a directory for each jurisdiction. The repository
currently only includes benchmark data for California state cases. Performing
well on the California cases will lead to performing well on all
U.S. jurisdictions.

A directory contains a number of YAML files. Each file represents one query and has the following fields:
* `query`: what a user types into the search box.
* `relevance_criteria`: a determination of the intent of the query and guidelines for scoring this query's search results.
* `cases`: a list of case results, each of which has:
  * `name`: a common name of the case, including citations
  * `relevance`: a score according to the query's `relevance_criteria`

Relevance scores are one of the four values:
1. `BEST`
2. `VERY_GOOD`
3. `GOOD`
4. `BAD`

# Use

To evaluate a list of search results, we use a standard information retrieval metric called [normalized discounted cumulative gain](https://en.wikipedia.org/wiki/Discounted_cumulative_gain#Normalized_DCG). This boils the search results into a single number, letting you compare one set of search results against another.
