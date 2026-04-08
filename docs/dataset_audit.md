# Dataset Audit

Dataset: `AUEB-NLP/ecthr_cases`
Task: `violation-prediction`

## Split Sizes
| split | num_records |
| --- | --- |
| train | 9000 |
| test | 1000 |
| validation | 1000 |

## Label Structure
- Feature names: ['facts', 'labels', 'silver_rationales']
- Label feature: `Sequence(feature=Value(dtype='string', id=None), length=-1, id=None)`
- Unique labels (29): 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 18, 34, 38, 46, P1-1, P1-2, P1-3, P12-1, P4-2, P4-4, P6-1, P6-3, P7-1, P7-2, P7-3, P7-4

### Labels Per Record
| split | labels_per_record | count | pct |
| --- | --- | --- | --- |
| train | 0 | 762 | 8.47 |
| train | 1 | 5237 | 58.19 |
| train | 2 | 2348 | 26.09 |
| train | 3 | 410 | 4.56 |
| train | 4 | 211 | 2.34 |
| train | 5 | 21 | 0.23 |
| train | 6 | 10 | 0.11 |
| train | 8 | 1 | 0.01 |
| test | 0 | 135 | 13.5 |
| test | 1 | 621 | 62.1 |
| test | 2 | 171 | 17.1 |
| test | 3 | 46 | 4.6 |
| test | 4 | 25 | 2.5 |
| test | 5 | 2 | 0.2 |
| validation | 0 | 148 | 14.8 |
| validation | 1 | 580 | 58.0 |
| validation | 2 | 207 | 20.7 |
| validation | 3 | 55 | 5.5 |
| validation | 4 | 9 | 0.9 |
| validation | 5 | 1 | 0.1 |

## Label Frequencies
| label | train_count | validation_count | test_count | train_pct |
| --- | --- | --- | --- | --- |
| 6 | 4704 | 300 | 299 | 52.27 |
| P1-1 | 1421 | 139 | 122 | 15.79 |
| 5 | 1368 | 187 | 166 | 15.2 |
| 3 | 1349 | 193 | 189 | 14.99 |
| 13 | 1238 | 88 | 79 | 13.76 |
| 8 | 710 | 87 | 123 | 7.89 |
| 2 | 505 | 57 | 56 | 5.61 |
| 10 | 291 | 42 | 77 | 3.23 |
| 14 | 141 | 18 | 16 | 1.57 |
| 11 | 110 | 33 | 37 | 1.22 |
| 34 | 75 | 21 | 16 | 0.83 |
| P1-3 | 48 | 9 | 2 | 0.53 |
| 9 | 41 | 4 | 5 | 0.46 |
| 38 | 35 | 1 | 1 | 0.39 |
| P4-2 | 35 | 5 | 4 | 0.39 |
| 7 | 29 | 3 | 3 | 0.32 |
| P1-2 | 17 | 1 | 4 | 0.19 |
| P7-2 | 16 | 1 | 2 | 0.18 |
| P7-4 | 16 | 4 | 2 | 0.18 |
| 12 | 6 | 1 | 0 | 0.07 |
| 4 | 6 | 1 | 1 | 0.07 |
| P7-1 | 6 | 1 | 1 | 0.07 |
| 18 | 4 | 1 | 6 | 0.04 |
| P4-4 | 3 | 3 | 0 | 0.03 |
| 46 | 2 | 0 | 0 | 0.02 |
| P12-1 | 1 | 0 | 0 | 0.01 |
| P6-1 | 1 | 0 | 0 | 0.01 |
| P6-3 | 1 | 0 | 0 | 0.01 |
| P7-3 | 1 | 0 | 0 | 0.01 |

## Example Records
### train[0]
- Labels: ['8']
- Fact paragraphs: 83
- Silver rationales: 19
- Paragraph 1: 11.  At the beginning of the events relevant to the application, K. had a daughter, P., and a son, M., born in 1986 and 1988 respectively. P.’s father is X and M.’s father is V. From March to May 1989 K. was voluntarily hospitalised for about three months, having been diagnosed a
- Paragraph 2: 12.  The applicants initially cohabited from the summer of 1991 to July 1993. In 1991 both P. and M. were living with them. From 1991 to 1993 K. and X were involved in a custody and access dispute concerning P. In May 1992 a residence order was made transferring custody of P. to 

### validation[0]
- Labels: []
- Fact paragraphs: 7
- Silver rationales: 0
- Paragraph 1: 5.  The applicant was born in 1983 and is detained in Sztum.
- Paragraph 2: 6.  At the time of the events in question, the applicant was serving a prison sentence in the Barczewo prison.

### test[0]
- Labels: ['10']
- Fact paragraphs: 37
- Silver rationales: 26
- Paragraph 1: 5.  The applicant is a journalist for DN.no, a Norwegian Internet-based version of the newspaper Dagens Næringsliv (“DN”), published by the company DN Nye Medier AS.
- Paragraph 2: 6.  On 23 June 2010 Mr X was indicted for market manipulation and insider trading under the 1997 Act on the Trade of Financial Assets (verdipapirhandelloven). He was accused of having requested Mr Y, an attorney, to draft a letter concerning the Norwegian Oil Company (“DNO”), a l
