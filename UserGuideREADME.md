# VotingPlatform User Guide

Welcome to the VotingPlatform! This decentralized application (DApp) allows you to conduct elections with registered candidates and voters on the Ethereum blockchain using the Solidity programming language.

## Smart Contract Overview

The VotingPlatform consists of the `Election` smart contract, which is responsible for managing the election process. It allows the admin to set up the election details, add candidates, register voters, verify voters, and conduct the voting process. The admin is the one who deploys the contract and has special privileges to manage the election.

## Basic Workflow

A brief explanation on the basic workflow of the application.

- Admin will create a voting instance by launching/deploying the application in a blockchain network (EVM), then create an election instance and start the election with the details of the election filled in (including candidates for voters to vote).
- Then the likely voters connect to the same blockchain network register to become a voter. Once the users successfully register, their respective details are sent/displayed in the admins' panel (i.e. verification page).
- The admin then will check if the registration information (blockchain account address, name, and phone number) is valid and matches with his record. If yes, then the admin approves the registered user making them eligible to take part and cast their respective vote in the election.
- The registered user (voter) following the approval from the admin casts their vote to the candidate of interest (from the voting page).
- After some time, depending on the scale of the election the admin ends the election. As that happens the voting is closed and the results are displayed announcing the winner at the top of the results page.

---

## Setting up the development environment

### Requirements

- Solidity compiler (>=0.4.21 <0.9.0)
- Ethereum blockchain network (EVM)
- Ethereum wallet (e.g., MetaMask)

---

## Contract Functions

### Election Contract Functions

1. **getAdmin():** Get the address of the admin who deployed the contract.

2. **addCandidate(string _header, string _slogan):** Add a new candidate to the election. Only the admin can perform this action.

3. **setElectionDetails(string _adminName, string _adminEmail, string _adminTitle, string _electionTitle, string _organizationTitle):** Set up the details of the election, including admin information and election titles. Only the admin can perform this action.

4. **getAdminName():** Get the name of the admin.

5. **getAdminEmail():** Get the email address of the admin.

6. **getAdminTitle():** Get the title of the admin.

7. **getElectionTitle():** Get the title of the election.

8. **getOrganizationTitle():** Get the title of the organization hosting the election.

9. **getTotalCandidate():** Get the total number of candidates registered for the election.

10. **getTotalVoter():** Get the total number of voters registered for the election.

11. **registerAsVoter(string _name, string _phone):** Register as a voter for the election by providing your name and phone number.

12. **verifyVoter(bool _verifedStatus, address voterAddress):** Verify a registered voter. Only the admin can perform this action.

13. **vote(uint256 candidateId):** Cast your vote for a specific candidate by providing the candidate ID. You can only vote once, and you must be a registered and verified voter.

14. **endElection():** End the election process. Only the admin can perform this action.

15. **getStart():** Get the status of the election (whether it has started or not).

16. **getEnd():** Get the status of the election (whether it has ended or not).

## How to Use the Application

### Step 1: Deploy the Contract

The Election contract needs to be deployed to the Ethereum network by the admin. The deployment process will require the admin's Ethereum address and can be done using tools like Remix IDE, Truffle, or Hardhat.

### Step 2: Set Up Election Details

Once the contract is deployed, the admin should set up the election details using the `setElectionDetails` function. Provide the necessary information, such as the admin's name, email, title, election title, and organization title.

### Step 3: Add Candidates

After setting up the election details, the admin can add candidates using the `addCandidate` function. Candidates need to be added before the election starts.

### Step 4: Register as a Voter

Any individual who wants to participate as a voter should register using the `registerAsVoter` function. Provide your name and phone number to register.

### Step 5: Verify Voters (Admin Only)

As the admin, you need to verify the registered voters before they can cast their votes. Use the `verifyVoter` function to verify a voter's status.

### Step 6: Start the Election

Once the candidates and voters are registered, the admin should start the election using the `setElectionDetails` function.

### Step 7: Cast Your Vote

Registered and verified voters can now cast their votes by calling the `vote` function with the candidate ID they want to vote for.

### Step 8: End the Election (Admin Only)

As the admin, you should end the election process using the `endElection` function once the voting period is over.

### Additional Functions

- You can check the status of the election (whether it has started or ended) by calling `getStart` and `getEnd` functions.

- You can retrieve election and admin details using various `get` functions provided in the contract.

## Important Notes

1. Make sure to double-check the candidate ID before casting your vote.

2. You can only vote once, and your vote cannot be changed once cast.

3. Only the admin has the privilege to add candidates, verify voters, and end the election.

4. It is recommended to use a well-known Ethereum wallet like MetaMask and interact with the contract through a reliable Ethereum client.

5. Once the election has ended, the results can be viewed by analyzing the votes received by each candidate.

## Conclusion

Congratulations! You are now ready to use the VotingPlatform. Please ensure to follow the guidelines and rules set by the admin for a fair and transparent election process. If you have any questions or encounter any issues, feel free to reach out to the admin or the support team.

Happy Voting!