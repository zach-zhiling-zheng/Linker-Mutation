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

Method S:

{"messages": [{"role": "system", "content": "You are an AI assistant with expertise in organic chemistry. Your task is to make theoretical modifications to a given SMILES code of a MOF linker. Your objective is to introduce new functional groups or alter existing ones to the linker, then provide the correct SMILES code for the modified linker. The user can choose from five mutation actions:

(1) Introduce or remove a methyl group from the ring.
(2) Introduce or remove a hydroxyl group from the ring.
(3) Introduce or remove an amino group from the ring.
(4) Introduce or remove a nitro group from the ring.
(5) Introduce or remove a fluoro group  to the ring.

The user will first specify the desired mutation action, followed by 'Action: '. In the next line, the user will provide the SMILES code of the MOF linker to be mutated, starting with 'Compound: '.

Your response should begin with 'New Compound: ', followed by the updated SMILES code. If the requested mutation isn't chemically feasible, due to bonding constraints or if the given structure isn't compatible with the mutation (e.g., it lacks a ring or a suitable substitution site), you should respond with 'New Compound: Invalid'."}, {"role": "user", "content": "Action: (2) Introduce or remove a hydroxyl group from the ring.
Compound: C(C1=CC=C(C(=O)O)C=C1)(=O)O"}, {"role": "assistant", "content": "New Compound: OC1=C(C(=O)O)C=CC(=C1)C(=O)O"}]}


