# Linker-Mutation
text here
<small>
| Mutation Method | Description | Consequence | Action 1 | Action 2 | Action 3 | Action 4 | Action 5 |
|-----------------|-------------|-------------|----------|----------|----------|----------|----------|
| Method S | Substitution of Functional Groups | Modify existing functional groups or introduce new ones to the linker. This can influence the MOF's interaction with guest molecules. | Introduce or remove a methyl group to the ring | Introduce or remove a hydroxyl group to the ring | Introduce or remove an amino group to the ring | Introduce or remove a nitro group to the ring | Introduce or remove a fluoro group to the ring |
| Method I | Insertion of Bonds and Rings | Insert or delete a linker expansion spacer like phenyl ring, double bond, triple bond, or azo group specifically at the location where a carboxylate group is directly connected to either a ring, a C=C double bond, a C#C triple bond, or an N=N azo group within the linker. This can alter the electronic properties, flexibility, and stability. | Insert or remove an unsubstituted phenyl ring at the connection where the carboxylate group is directly attached to either a ring, C=C, C#C, or N=N, ensuring para-positioning | Insert or remove two carbons along with a triple bond at the connection where the carboxylate group is directly attached to either a ring, C=C, C#C, or N=N | Insert or remove two carbons along with a double bond at the connection where the carboxylate group is directly attached to either a ring, C=C, C#C, or N=N | Insert or remove an azo group (-N=N-) at the connection where the carboxylate group is directly attached to either a ring, C=C, C#C, or N=N | / |
| Method R | Heteroatom Replacement | Swap out atoms in the linker with different heteroatoms (e.g., replace a carbon atom with a nitrogen or sulfur atom). This can introduce new electronic properties or bonding motifs. | Replace a carbon atom in the ring with nitrogen, or vice versa | Replace a carbon atom in the ring with oxygen, or vice versa | Replace a carbon atom in the ring with sulfur, or vice versa | / | / |
| Method P | Coordination Site Positional Isomerization | Change the position of coordination sites like COOH or N within aromatic or non-aromatic rings, including 5-membered, 6-membered, 7-membered, and fused rings. This can modify the topology and geometry of the resulting MOF, influencing its properties. | Shift the position of a COOH group within any ring type to another position on the same ring | Relocate the position of N donor, excluding NH, within any ring type to another position on the same ring | / | / | / |

</small>

Example:

**Method S:**

{"messages": [{"role": "system", "content": "You are an AI assistant with expertise in organic chemistry. Your task is to make theoretical modifications to a given SMILES code of a MOF linker. Your objective is to introduce new functional groups or alter existing ones to the linker, then provide the correct SMILES code for the modified linker. The user can choose from five mutation actions:

(1) Introduce or remove a methyl group from the ring.
(2) Introduce or remove a hydroxyl group from the ring.
(3) Introduce or remove an amino group from the ring.
(4) Introduce or remove a nitro group from the ring.
(5) Introduce or remove a fluoro group  to the ring.

The user will first specify the desired mutation action, followed by 'Action: '. In the next line, the user will provide the SMILES code of the MOF linker to be mutated, starting with 'Compound: '.

Your response should begin with 'New Compound: ', followed by the updated SMILES code. If the requested mutation isn't chemically feasible, due to bonding constraints or if the given structure isn't compatible with the mutation (e.g., it lacks a ring or a suitable substitution site), you should respond with 'New Compound: Invalid'."}, {"role": "user", "content": "Action: (2) Introduce or remove a hydroxyl group from the ring.
Compound: C(C1=CC=C(C(=O)O)C=C1)(=O)O"}, {"role": "assistant", "content": "New Compound: OC1=C(C(=O)O)C=CC(=C1)C(=O)O"}]}


**Method I:**

"{""messages"": [{""role"": ""system"", ""content"": ""You are an AI assistant with expertise in organic chemistry. Your task is to make theoretical modifications to a given SMILES code of a MOF linker. Your objective is to insert or delete a linker expansion spacer like phenyl ring, double bond, triple bond, or azo group specifically at the location where a carboxylate group is directly connected to either a ring, a C=C double bond, a C#C triple bond, or an N=N azo group within the linker, then provide the correct SMILES code for the modified linker. The user can choose from four mutation actions:

(1) Insert or remove an unsubstituted phenyl ring at the connection where the carboxylate group is directly attached to either a ring, C=C, C#C, or N=N, ensuring para-positioning.
(2) Insert or remove two carbons along with a triple bond at the connection where the carboxylate group is directly attached to either a ring, C=C, C#C, or N=N.
(3) Insert or remove two carbons along with a double bond at the connection where the carboxylate group is directly attached to either a ring, C=C, C#C, or N=N.
(4) Insert or remove an azo group (-N=N-) at the connection where the carboxylate group is directly attached to either a ring, C=C, C#C, or N=N.

The user will first specify the desired mutation action, followed by 'Action: '. In the next line, the user will provide the SMILES code of the MOF linker to be mutated, starting with 'Compound: '.

Your response should begin with 'New Compound: ', followed by the updated SMILES code. If the requested mutation isn't chemically feasible, due to bonding constraints or if the given structure isn't compatible with the mutation (e.g., it lacks a ring or a suitable insertion site between carboxylate and qualified qualified structural groups mentioned above), you should respond with 'New Compound: Invalid'.""}, {""role"": ""user"", ""content"": ""Action: (3) Introduce or remove a double bond within the linker.
Compound: C(C1=CC=C(C(=O)O)C=C1)(=O)O""}, {""role"": ""assistant"", ""content"": ""New Compound: C(=O)(O)C=CC1=CC=C(C(=O)O)C=C1""}]}"						



**Method R:**

"{""messages"": [{""role"": ""system"", ""content"": ""You are an AI assistant with expertise in organic chemistry. Your task is to make theoretical modifications to a given SMILES code of a MOF linker. Your objective is to swap out atoms in the linker with different heteroatoms (e.g., replace a carbon atom with a nitrogen or sulfur atom), while adhering to general chemical rules and bonding constraints, such as ensuring ring stability and proper valence for atoms. The user can choose from three mutation actions:

(1) Replace a carbon atom in the ring with nitrogen, or vice versa.
(2) Replace a carbon atom in the ring with oxygen, or vice versa.
(3) Replace a carbon atom in the ring with sulfur, or vice versa.

The user will first specify the desired mutation action, followed by 'Action: '. In the next line, the user will provide the SMILES code of the MOF linker to be mutated, starting with 'Compound: '.

Your response should begin with 'New Compound: ', followed by the updated SMILES code. If the requested mutation isn't chemically feasible, due to bonding constraints or if the given structure isn't compatible with the mutation (e.g., it lacks a ring or a suitable substitution site), you should respond with 'New Compound: Invalid'.""}, {""role"": ""user"", ""content"": ""C(C1=CC=C(C(=O)O)C=C1)(=O)O""},  {""role"": ""user"", ""content"": ""Action: (1) Replace a carbon atom in the ring with nitrogen, or vice versa.
Compound: C(C1=CC=C(C(=O)O)C=C1)(=O)O""}, {""role"": ""assistant"", ""content"": ""New Compound: N1=C(C=CC(=C1)C(=O)O)C(=O)O""}]}"						



**Method P：**


"{""messages"": [{""role"": ""system"", ""content"": ""You are an AI assistant with expertise in organic chemistry. Your task is to make theoretical modifications to a given SMILES code of a MOF linker. Your objective is to change the position of coordination sites, such as COOH or N, within aromatic or non-aromatic rings including 5-membered, 6-membered, 7-membered, and fused rings. The user can choose from two mutation actions:

(1) Shift the position of a COOH group within any ring type to another position on the same ring.
(2) Relocate the position of N donor, excluding NH, within any ring type to another position on the same ring.

The user will first specify the desired mutation action, followed by 'Action: '. In the next line, the user will provide the SMILES code of the MOF linker to be mutated, starting with 'Compound: '.

Your response should begin with 'New Compound: ', followed by the updated SMILES code. If the requested mutation isn't chemically feasible, due to bonding constraints or if the given structure isn't compatible with the mutation (e.g., it lacks a ring or a suitable position for the coordination site shift), you should respond with 'New Compound: Invalid'.""}, {""role"": ""user"", ""content"": ""C(C1=CC=C(C(=O)O)C=C1)(=O)O""},  {""role"": ""user"", ""content"": ""Action: (1) Shift the position of COOH within any ring type to another position on the same ring.
Compound: C(C1=CC=C(C(=O)O)C=C1)(=O)O""}, {""role"": ""assistant"", ""content"": ""New Compound: C1=CC(=CC(=C1)C(=O)O)C(=O)O""}]}"						





**Summary：**


| Model | Chemical representations | Number of datapoints | Total mutations | Input System Prompt | Input User Message | Training Cost for all 4 sub models | Output Fine-tune model names |
|-------|--------------------------|----------------------|-----------------|---------------------|--------------------|-----------------------------------|-----------------------------|
| Model 1X | Train full set of SMILES, including hypothetical structures | Method R: 700, S: 1990, I:746, P:507 | 3943 | ...SMILES code of a MOF linker | Action: (1) Replace a carbon atom in the ring with nitrogen, or vice versa. | 2M tokens / ~20 USD | Model 1S, Model 1I, Model 1R, Model 1P |
| Model 2X | Train full set of SELFIES strings converted from SMILES code | Method R: 700, S: 1990, I:746, P:507 | 3943 | ...SELFIES string of a MOF linker. Here, SELFIES (SELF-referencing Embedded Strings) is a string-based representation of molecules. Every SELFIES string corresponds to a valid molecule, similar to how SMILES representations work. | Action: (1) Replace a carbon atom in the ring with nitrogen, or vice versa. | 4M tokens / ~40 USD | Model 2S, Model 2I, Model 2R, Model 2P |
| Model 3X | Train IUPAC names found in PubChem, plus those converted by Syntelly using SMILES | Method R: 700, S: 1970, I:746, P:504 | 3920 | ...IUPAC name of a MOF linker | Action: (1) Replace a carbon atom in the ring with nitrogen, or vice versa. | 2M tokens / ~20 USD | Model 3S, Model 3I, Model 3R, Model 3P |



**Model IDs:**


Model 1R (SMMILES): "ft:gpt-3.5-turbo-0613:uc-berkeley::7vd4eEZu"
Model 2R (SELFIES):  "ft:gpt-3.5-turbo-0613:uc-berkeley::7veHJ0eR"  
Model 3R (IUPAC): "ft:gpt-3.5-turbo-0613:uc-berkeley::7vyL332G"

Model 1S (SMMILES): "ft:gpt-3.5-turbo-0613:uc-berkeley::7wF4Wvdr"
Model 2S (SELFIES):  "ft:gpt-3.5-turbo-0613:uc-berkeley::7wGGcyfU"  
Model 3S (IUPAC): "ft:gpt-3.5-turbo-0613:uc-berkeley::7wHSe0sw"

Model 1I (SMMILES): "ft:gpt-3.5-turbo-0613:uc-berkeley::7xJmyNlq"
Model 2I (SELFIES):  "ft:gpt-3.5-turbo-0613:uc-berkeley::7xKePzT5"  
Model 3I (IUPAC): "ft:gpt-3.5-turbo-0613:uc-berkeley::7xM2Vcbv"

Model 1P (SMMILES): "ft:gpt-3.5-turbo-0613:uc-berkeley::7xiQHz21"
Model 2P (SELFIES):  "ft:gpt-3.5-turbo-0613:uc-berkeley::7xjKObLF"  
Model 3P (IUPAC): "ft:gpt-3.5-turbo-0613:uc-berkeley::7xkDldW9"


![image](https://github.com/zach-zhiling-zheng/Linker-Mutation/assets/107890298/d8bd4e2a-08ca-42fb-99ac-af3c5d3bf18a)








