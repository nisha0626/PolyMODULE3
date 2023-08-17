# ZK SNARK Designer
This aim of the project is  to implement a logical gate circuit using the circom programming language and provide a Zero-Knowledge Succinct Non-Interactive Argument of Knowledge (ZK-SNARK) proof to demonstrate the knowledge of specific inputs that yield a particular output.
For this project, you will create a circuit using the circom programming language that implements  logical gate:

## Circuit Logic
The logical gate circuit has the following truth table:

| A | B | X | Y | Q |
|---|---|---|---|---|
| 0 | 0 | 0 | 1 | 1 |
| 0 | 1 | 0 | 0 | 0 |
| 1 | 0 | 0 | 1 | 1 |
| 1 | 1 | 1 | 0 | 1 |

The goal is to prove that we know the inputs A (0) and B (1) that yield a 0 output (Q = 0).

### Steps Involved
To successfully complete the project, the following steps will be undertaken:

1. Write a Correct Circuit Implementation: Implement the logical gate circuit using the circom programming language.

2. Compile the Circuit: Compile the circuit to generate circuit intermediaries.

3. Generate a ZK-SNARK Proof: Generate a ZK-SNARK proof using the specified inputs A=0 and B=1.

4. Deploy a Solidity Verifier Contract: Deploy a solidity verifier contract on the Sepolia or Mumbai Testnet.

5. Verify the Proof: Call the verifyProof() method on the deployed verifier contract and assert that the output is true.

### Quick Start
To quickly get started, follow these steps:

.Install all dependencies by running npm i.

.Compile the circuit using the command: npx hardhat circom. 
This will generate the out directory with circuit intermediaries and the CustomCircuitSVerifier.sol contract.

### Prove and Deploy:

Run npx hardhat run scripts/deploy.ts. This script performs the following tasks:-
Deploys the CustomCircuitVerifier.sol contract.

Generates a proof from circuit intermediaries using generateProof().

Generates calldata with generateCallData().

Calls verifyProof() on the verifier contract with the calldata.

Configuration
Each new circuit lives in its own directory. At the top level of each circuit directory resides the circom circuit and input to the circuit. The out directory will be auto-generated and store the compiled outputs, keys, and proofs. The Powers of Tau file comes from the Polygon Hermez ceremony, which saves time by not needing a new ceremony.

Verifier contracts are autogenerated and prefixed by the circuit name.

### Transaction
To deploy the project on the Mumbai Testnet, run the following command:
npx hardhat run scripts/deploy.ts --network mumbai

Check for the successful transaction and verify fulfillment in the Mumbai PolygonScan by searching with the provided contract address.

### Author
NISHA KUMARI

