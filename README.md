# Linker-Mutation

<img src="./docs/images/logo.png" width="20%" height="20%">

## Summary of different linker mutation methods

### Method S:

Substitution of Functional Groups by modifying existing functional groups or introducing new ones to the linker:

```python
{"messages": [{"role": "system", "content": "You are an AI assistant with expertise in organic chemistry. Your task is to make theoretical modifications to a given SMILES code of a MOF linker. Your objective is to introduce new functional groups or alter existing ones to the linker, then provide the correct SMILES code for the modified linker. The user can choose from five mutation actions:

(1) Introduce or remove a methyl group from the ring.
(2) Introduce or remove a hydroxyl group from the ring.
(3) Introduce or remove an amino group from the ring.
(4) Introduce or remove a nitro group from the ring.
(5) Introduce or remove a fluoro group from the ring.

The user will first specify the desired mutation action, followed by 'Action: '. In the next line, the user will provide the SMILES code of the MOF linker to be mutated, starting with 'Compound: '.

Your response should begin with 'New Compound: ', followed by the updated SMILES code. If the requested mutation isn't chemically feasible, due to bonding constraints or if the given structure isn't compatible with the mutation (e.g., it lacks a ring or a suitable substitution site), you should respond with 'New Compound: Invalid'."}, {"role": "user", "content": "Action: (2) Introduce or remove a hydroxyl group from the ring.
Compound: C(C1=CC=C(C(=O)O)C=C1)(=O)O"}, {"role": "assistant", "content": "New Compound: OC1=C(C(=O)O)C=CC(=C1)C(=O)O"}]}
```

### Method I:

Insertion of Bonds and Rings by either inserting or deleting a linker expansion spacer like phenyl ring, double bond, triple bond, or azo group specifically at the location where a carboxylate group is directly connected to either a ring, a C=C double bond, a C $\equiv$ C triple bond, or an N=N azo group within the linker:

```python
"{""messages"": [{""role"": ""system"", ""content"": ""You are an AI assistant with expertise in organic chemistry. Your task is to make theoretical modifications to a given SMILES code of a MOF linker. Your objective is to insert or delete a linker expansion spacer like phenyl ring, double bond, triple bond, or azo group specifically at the location where a carboxylate group is directly connected to either a ring, a C=C double bond, a C#C triple bond, or an N=N azo group within the linker, then provide the correct SMILES code for the modified linker. The user can choose from four mutation actions:

(1) Insert or remove an unsubstituted phenyl ring at the connection where the carboxylate group is directly attached to either a ring, C=C, C#C, or N=N, ensuring para-positioning.
(2) Insert or remove two carbons along with a triple bond at the connection where the carboxylate group is directly attached to either a ring, C=C, C#C, or N=N.
(3) Insert or remove two carbons along with a double bond at the connection where the carboxylate group is directly attached to either a ring, C=C, C#C, or N=N.
(4) Insert or remove an azo group (-N=N-) at the connection where the carboxylate group is directly attached to either a ring, C=C, C#C, or N=N.

The user will first specify the desired mutation action, followed by 'Action: '. In the next line, the user will provide the SMILES code of the MOF linker to be mutated, starting with 'Compound: '.

Your response should begin with 'New Compound: ', followed by the updated SMILES code. If the requested mutation isn't chemically feasible, due to bonding constraints or if the given structure isn't compatible with the mutation (e.g., it lacks a ring or a suitable insertion site between carboxylate and qualified qualified structural groups mentioned above), you should respond with 'New Compound: Invalid'.""}, {""role"": ""user"", ""content"": ""Action: (3) Introduce or remove a double bond within the linker.
Compound: C(C1=CC=C(C(=O)O)C=C1)(=O)O""}, {""role"": ""assistant"", ""content"": ""New Compound: C(=O)(O)C=CC1=CC=C(C(=O)O)C=C1""}]}"						
```


### Method R:

Heteroatom Replacement by swapping out atoms in the linker with different heteroatoms (e.g., replace a carbon atom with a nitrogen or sulfur atom):

```python
"{""messages"": [{""role"": ""system"", ""content"": ""You are an AI assistant with expertise in organic chemistry. Your task is to make theoretical modifications to a given SMILES code of a MOF linker. Your objective is to swap out atoms in the linker with different heteroatoms (e.g., replace a carbon atom with a nitrogen or sulfur atom), while adhering to general chemical rules and bonding constraints, such as ensuring ring stability and proper valence for atoms. The user can choose from three mutation actions:

(1) Replace a carbon atom in the ring with nitrogen, or vice versa.
(2) Replace a carbon atom in the ring with oxygen, or vice versa.
(3) Replace a carbon atom in the ring with sulfur, or vice versa.

The user will first specify the desired mutation action, followed by 'Action: '. In the next line, the user will provide the SMILES code of the MOF linker to be mutated, starting with 'Compound: '.

Your response should begin with 'New Compound: ', followed by the updated SMILES code. If the requested mutation isn't chemically feasible, due to bonding constraints or if the given structure isn't compatible with the mutation (e.g., it lacks a ring or a suitable substitution site), you should respond with 'New Compound: Invalid'.""}, {""role"": ""user"", ""content"": ""C(C1=CC=C(C(=O)O)C=C1)(=O)O""},  {""role"": ""user"", ""content"": ""Action: (1) Replace a carbon atom in the ring with nitrogen, or vice versa.
Compound: C(C1=CC=C(C(=O)O)C=C1)(=O)O""}, {""role"": ""assistant"", ""content"": ""New Compound: N1=C(C=CC(=C1)C(=O)O)C(=O)O""}]}"						
```


### Method P：

Coordination Site Positional Isomerization by changing the position of coordination sites like COOH or N within aromatic or non-aromatic rings, including 5-membered, 6-membered, 7-membered, and fused rings:

```python
"{""messages"": [{""role"": ""system"", ""content"": ""You are an AI assistant with expertise in organic chemistry. Your task is to make theoretical modifications to a given SMILES code of a MOF linker. Your objective is to change the position of coordination sites, such as COOH or N, within aromatic or non-aromatic rings including 5-membered, 6-membered, 7-membered, and fused rings. The user can choose from two mutation actions:

(1) Shift the position of a COOH group within any ring type to another position on the same ring.
(2) Relocate the position of N donor, excluding NH, within any ring type to another position on the same ring.

The user will first specify the desired mutation action, followed by 'Action: '. In the next line, the user will provide the SMILES code of the MOF linker to be mutated, starting with 'Compound: '.

Your response should begin with 'New Compound: ', followed by the updated SMILES code. If the requested mutation isn't chemically feasible, due to bonding constraints or if the given structure isn't compatible with the mutation (e.g., it lacks a ring or a suitable position for the coordination site shift), you should respond with 'New Compound: Invalid'.""}, {""role"": ""user"", ""content"": ""C(C1=CC=C(C(=O)O)C=C1)(=O)O""},  {""role"": ""user"", ""content"": ""Action: (1) Shift the position of COOH within any ring type to another position on the same ring.
Compound: C(C1=CC=C(C(=O)O)C=C1)(=O)O""}, {""role"": ""assistant"", ""content"": ""New Compound: C1=CC(=CC(=C1)C(=O)O)C(=O)O""}]}"						
```

## Summary of the different chemical representations considered

> [!NOTE]
> The 'X' here could be either R, S, I, or P depending on the linker mutation method used (as described above)

> [!IMPORTANT]
> :key: denotes the model ID of the fine-tuned sub-model <br>
> :moneybag: denotes the training cost for all the fine-tuned sub-models

### Model 1X 

Chemical Representation: `SMILES`

Description: `Train full set of SMILES, including hypothetical structures`

Number of data points (Total=3943): 

- [x] Method R: 700 --> **Model 1R** --> :key: `ft:gpt-3.5-turbo-0613:uc-berkeley::7vd4eEZu`
- [x] Method S: 1990 --> **Model 1S** --> :key: `ft:gpt-3.5-turbo-0613:uc-berkeley::7wF4Wvdr`
- [x] Method I: 746 --> **Model 1I** --> :key: `ft:gpt-3.5-turbo-0613:uc-berkeley::7xJmyNlq`
- [x] Method P: 507 --> **Model 1P** --> :key: `ft:gpt-3.5-turbo-0613:uc-berkeley::7xiQHz21`

:moneybag: $20 for every 2M tokens

### Model 2X 

Chemical Representation: `SELFIES`

Description: `Train full set of SELFIES strings converted from SMILES code`

Number of data points (Total=3943): 

- [x] Method R: 700 --> **Model 2R** --> :key: `ft:gpt-3.5-turbo-0613:uc-berkeley::7veHJ0eR`
- [x] Method S: 1990 --> **Model 2S** --> :key: `ft:gpt-3.5-turbo-0613:uc-berkeley::7wGGcyfU`
- [x] Method I: 746 --> **Model 2I** --> :key: `ft:gpt-3.5-turbo-0613:uc-berkeley::7xKePzT5`
- [x] Method P: 507 --> **Model 2P** --> :key: `ft:gpt-3.5-turbo-0613:uc-berkeley::7xjKObLF`

:moneybag: $20 for every 2M tokens   

### Model 3X 

Chemical Representation: `IUPAC`

Description: `Train IUPAC names found in PubChem, plus those converted by Syntelly using SMILES`

Number of data points (Total=3920): 

- [x] Method R: 700 --> **Model 3R** --> :key: `ft:gpt-3.5-turbo-0613:uc-berkeley::7vyL332G`
- [x] Method S: 1970 --> **Model 3S** --> :key: `ft:gpt-3.5-turbo-0613:uc-berkeley::7wHSe0sw`
- [x] Method I: 746 --> **Model 3I** --> :key: `ft:gpt-3.5-turbo-0613:uc-berkeley::7xM2Vcbv`
- [x] Method P: 507 --> **Model 3P** --> :key: `ft:gpt-3.5-turbo-0613:uc-berkeley::7xkDldW9`

:moneybag: $20 for every 2M tokens   

## Performance of the different models

> [!NOTE]
> TP = True Positive <br>
> TN = True Negative <br>
> FP = False Positive <br>
> FN = False Negative <br>
> GPT-3.5 refers to the 'Insert exact model ID' without fine-tuning <br>
> GPT-4 refers to the 'Insert exact model ID' without finetuning

### For all the methods (method S + I + R + P) combined: 

| Model | Format | TP | TN | FP | FN | Total | Accuracy (%) | Precision (%) | Recall (%) | F1 Score (%) |  
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| GPT-3.5 | SMILES | 27 | 16 | 320 | 57 | 420 | 10.2 | 7.8 | 32.1 | 12.5 |
| GPT-3.5 | IUPAC | 47 | 17 | 301 | 55 | 420 | 15.2 | 13.5 | 46.1 | 20.9 |
| GPT-4 | SMILES | 77 | 58 | 271 | 14 | 420 | 32.1 | 22.1 | 84.6 | 35.1 |
| GPT-4 | IUPAC | 95 | 70 | 248 | 7 | 420 | 39.3 | 27.7 | 93.1 | 42.7 |
| Model 1 | SMILES | 231 | 125 | 49 | 15 | 420 | 84.8 | 82.5 | 93.9 | 87.8 |
| Model 2 | SELFIES | 125 | 120 | 153 | 22 | 420 | 58.3 | 45.0 | 85.0 | 58.8 |
| Model 3 | IUPAC | 250 | 112 | 49 | 9 | 420 | <b>86.2</b> | <b>83.6</b> | <b>96.5</b> | <b>89.6</b> |

<details>
  <summary><i>For only the <b>method S</b> task: </i></summary>

  | Model | Format | TP | TN | FP | FN | Total | Accuracy (%) | Precision (%) | Recall (%) | F1 Score (%) |  
  | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
  | GPT-3.5 | SMILES | 9 | 0 | 116 | 25 | 150 | 6.0 | 7.2 | 26.5 | 11.3 |
  | GPT-3.5 | IUPAC | 35 | 1 | 108 | 6 | 150 | 24.0 | 24.5 | 85.4 | 38.0 |
  | GPT-4 | SMILES | 39 | 13 | 92 | 6 | 150 | 34.7 | 29.8 | 86.7 | 44.3 |
  | GPT-4 | IUPAC | 74 | 16 | 56 | 4 | 150 | 60.0 | 56.9 | 94.9 | 71.2 |
  | Model 1S | SMILES | 93 | 23 | 34 | 0 | 150 | 77.3 | 73.2 | <b>100.0</b> | 84.5 |
  | Model 2S | SELFIES | 7 | 19 | 117 | 7 | 150 | 17.3 | 5.6 | 50.0 | 10.1 |
  | Model 3S | IUPAC | 116 | 18 | 16 | 0 | 150 | <b>89.3</b> | <b>87.9</b> | <b>100.0</b> | <b>93.5</b> |

</details>

<details>
  <summary><i>For only the <b>method I</b> task: </i></summary>

  | Model | Format | TP | TN | FP | FN | Total | Accuracy (%) | Precision (%) | Recall (%) | F1 Score (%) |  
  | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
  | GPT-3.5 | SMILES | 15 | 0 | 83 | 22 | 120 | 12.5 | 15.3 | 40.5 | 22.2 |
  | GPT-3.5 | IUPAC | 2 | 1 | 91 | 26 | 120 | 2.5 | 2.2 | 7.1 | 3.3 |
  | GPT-4 | SMILES | 22 | 5 | 88 | 5 | 120 | 22.2 | 20.0 | 81.5 | 32.1 |
  | GPT-4 | IUPAC | 6 | 3 | 111 | 0 | 120 | 7.5 | 5.1 | <b>100.0</b> | 9.8 |
  | Model 1I | SMILES | 105 | 10 | 3 | 2 | 120 | <b>95.8</b> | <b>97.2</b> | 98.1 | <b>97.7</b> |
  | Model 2I | SELFIES | 94 | 12 | 12 | 2 | 120 | 88.3 | 88.7 | 97.9 | 93.1 |
  | Model 3I | IUPAC | 101 | 6 | 11 | 2 | 120 | 89.2 | 90.2 | 98.1 | 94.0 |

</details>

<details>
  <summary><i>For only the <b>method R</b> task: </i></summary>

  | Model | Format | TP | TN | FP | FN | Total | Accuracy (%) | Precision (%) | Recall (%) | F1 Score (%) |  
  | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
  | GPT-3.5 | SMILES | 1 | 7 | 82 | 0 | 90 | 8.9 | 1.2 | <b>100.0</b> | 2.4 |
  | GPT-3.5 | IUPAC | 2 | 7 | 68 | 13 | 90 | 10.0 | 2.9 | 13.3 | 4.7 |
  | GPT-4 | SMILES | 9 | 14 | 67 | 0 | 90 | 25.6 | 11.8 | <b>100.0</b> | 21.2 |
  | GPT-4 | IUPAC | 2 | 30 | 57 | 1 | 90 | 35.6 | 3.4 | 66.7 | 6.5 |
  | Model 1R | SMILES | 19 | 60 | 5 | 6 | 90 | <b>87.8</b> | <b>79.2</b> | 76.0 | <b>77.6</b> |
  | Model 2R | SELFIES | 16 | 60 | 9 | 5 | 90 | 84.4 | 64.0 | 76.2 | 69.6 |
  | Model 3R | IUPAC | 13 | 58 | 16 | 3 | 90 | 78.9 | 44.8 | 81.3 | 57.8 |

</details>

<details>
  <summary><i>For only the <b>method P</b> task: </i></summary>

  | Model | Format | TP | TN | FP | FN | Total | Accuracy (%) | Precision (%) | Recall (%) | F1 Score (%) |  
  | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
  | GPT-3.5 | SMILES | 2 | 9 | 39 | 10 | 60 | 18.3 | 4.9 | 16.7 | 7.5 |
  | GPT-3.5 | IUPAC | 8 | 8 | 34 | 10 | 60 | 26.7 | 19.0 | 44.4 | 26.7 |
  | GPT-4 | SMILES | 7 | 26 | 24 | 3 | 60 | 55.0 | 22.6 | 70.0 | 34.1 |
  | GPT-4 | IUPAC | 13 | 21 | 24 | 2 | 60 | 56.7 | 35.1 | <b>86.7</b> | 50.0 |
  | Model 1P | SMILES | 14 | 32 | 7 | 7 | 60 | 76.7 | 66.7 | 66.7 | 66.7 |
  | Model 2P | SELFIES | 8 | 29 | 15 | 8 | 60 | 61.7 | 34.8 | 50.0 | 41.0 |
  | Model 3P | IUPAC | 20 | 30 | 6 | 4 | 60 | <b>83.3</b> | <b>76.9</b> | 83.3 | <b>80.0</b> |

</details>


## License 

The input prompt generation script is distributed under the MIT open source license (see [`LICENSE.txt`](LICENSE.txt))


## Contributing

If you have any questions/comments/feedback, please feel free to reach out to any of the authors.

In addition, if you have any new feature requests or if you find any bugs, please open a new [issue](https://github.com/zach-zhiling-zheng/Linker-Mutation/issues).

## Acknowledgements

We acknowledge the financial support from the following sources:
1. Defense Advanced Research Projects Agency (DARPA) under contract HR0011-21-C-0020 
2. Bakar Institute of Digital Materials for the Planet (BIDMaP)
3. NIH (Grant S10-RR027172)
4. Kavli ENSI Graduate Student Fellowship

## References
For this work:

https://pubs.acs.org/doi/full/10.1021/jacs.3c12086
https://pubs.acs.org/doi/suppl/10.1021/jacs.3c12086/suppl_file/ja3c12086_si_001.pdf


For GPT-4: 

> GPT-4 Technical Report <br/>
> OpenAI <br/>
> https://arxiv.org/abs/2303.08774 <br/>









