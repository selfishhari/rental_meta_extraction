# rental_meta_extraction
extraction of metadata from rental agreements. BERT-NER

# Instructions to run:
1. Clone the repo
`git clone https://github.com/selfishhari/rental_meta_extraction.git`

2. Run notebooks/01_data_prep_rental_meta_extraction.ipynb and 02_bert_ner_rental_agreements.ipynb

# Approach
1. Use the provided annotations to create BIO tags.
2. The context about a Party is found to have been present in adjacent paragraphs, hence I combined 2-3 paragraphs in a rolling window fashion
3. The annotations are very noisy. Hence several cleaning techniques had to be formulated. Eg: Omitted initials(single letter tokens), Removed Mr, cleaned "."/"," etc..
4. Undersampled those paragraphs where only "O" tags were present

# Result
Bert as expected performs extremely well with as small as 600 samples. Validation F1 Score reached 90+ in just 25 epochs
