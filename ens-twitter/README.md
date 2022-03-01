# Twitter 🤝 ENS

Twitter is a bridge from Web2 social to Web3 social, as many Twitter users associate their ENS (which can be used to look up their wallet address) with their Twitter.

The ens-twitter pipeline is designed to link Twitter accounts to ENS names.

## Guiding principles

## Objectives

1. Ingest Twitter accounts that associate themselves with an ENS name
2. Extract the ENS name and associate with the Twitter account
3. Look up the wallet address associated with the ENS name, map to ENS name
4. Ingest results into Neo4J

## Process
*Outlined in greater depth in `twitter_ens_script.ipynb`*

1. Get baseline dataset of Twitter accounts that mention an ENS name in their name, bio, or handle from Ultra Sound Money.
2. Parse for ENS names.
3. Validate ENS names.
4. Look-up address associated with ENS name.
	- The address provided by `web3.py` is the `Controller`
5. Ingest into Neo4J rougly corresponding with this ontology. https://arrows.app/#/local/id=S4DvRHO9HLbz0XFETcI3




## Todos
1. I was only able to extract a valid ENS name for 66% of the accounts. If you have regex skills you could help improve our ENS name parser to improve coverage.
2. We are missing the `tokenId` associated with each ENS name. We need that to capture the `registrant` for the ENS name. 
3. We could/should expand beyond the UltraSound pipeline. As a starting point, we could run it again and capture the diff. We could also do a more general search for people who `dropped` their ENS in response to a thread. We could do some interesting analysis by looking at what type of threads people drop their ENS names for!
4. Once we feel comfortable about coverage, we should set up a pipeline for updates.
- Capturing new ENS/Twitter linkages
- Verifying existing ones.

