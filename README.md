# Learning Bitcoin from the Command Line - Week 5: Relative Timelocks

## Overview

This week, you will learn how to use relative timelocks in Bitcoin transactions. Relative timelocks are used to create input-specific locks. A transaction can be locked up to a certain number of blocks since the block in which the input it is referring to has been mined.

## Problem Statement

Relative timelocks are used to make input-specific locks. Using relative timelock, a transaction can be locked up to a certain number of blocks since the block in which the input it is referring to has been mined.

The exercise below demonstrates using a relative timelock spend.

## Solution Requirements

You need to write a bash script that will do the following:

### Setting up a relative timelock

1. Create two wallets: `Miner`, `Alice`.
2. Fund the wallets by generating some blocks for `Miner` and sending some coins to `Alice`.
3. Confirm the transaction and assert that `Alice` has a positive balance.
4. Create a **refund** transaction where `Alice` pays 10 BTC back to `Miner`, but with a relative timelock of 10 blocks.
5. Report in the terminal output what happens when you try to broadcast the refund transaction.

### Spend from relative timeLock

1. Generate 10 more blocks.
2. Broadcast the refund transaction. Confirm it by generating one more block.
3. Report Balance of `Alice`.

### Output Format

Output the txid of the refund transaction to `out.txt`. The file should contain the following structure:

```txt
<txid_refund>
```

## Submission

- Write your solution in `solution.sh`. Make sure to include comments explaining each step of your code.
- Commit your changes and push to the main branch:
    - Add your changes by running `git add solution.sh`.
    - Commit the changes by running `git commit -m "Solution"`.
    - Push the changes by running `git push origin main`.
- The autograder will run your script against a test script to verify the functionality.
- Check the status of the autograder on the Github Classroom portal to see if it passed successfully or failed. Once you pass the autograder with a score of 100, you have successfully completed the challenge.
- You can submit multiple times before the deadline. The last submission before the deadline will be considered your final submission.
- You will lose access to the repository after the deadline.

## Local Testing

### Prerequisites
- Install `jq` tool for parsing JSON data if you don't have it installed.
- Install Node.js and npm to run the test script.
- Node version 20 or higher is recommended. You can install Node.js using the following command:
  ```
  curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.5/install.sh | bash
  source ~/.nvm/nvm.sh
  nvm install 20
  ```
- Install the required npm packages by running `npm install`.

### Testing Steps
- Start your Bitcoin Core node with the `bitcoin.conf` file with the following parameters:
  ```
  regtest=1
  fallbackfee=0.0001
  server=1
  rest=1
  txindex=1
  rpcauth=alice:88cae77e34048eff8b9f0be35527dd91$d5c4e7ff4dfe771808e9c00a1393b90d498f54dcab0ee74a2d77bd01230cd4cc
  ```
- Run your script using the command `/bin/bash solution.sh`.
- Run the test script using the command `npm run test`.
- The test script will run your script and verify the output. If the test script passes, you have successfully completed the challenge and are ready to submit your solution.

### Common Issues
- Make sure Bitcoin Core is running before running the test script. Your submission should not stop the Bitcoin Core daemon at any point.
- Make sure your `bitcoin.conf` file is correctly configured with the required parameters.
- Linux and MacOS are the recommended operating systems for this challenge. If you are using Windows, you may face compatibility issues.
- The autograder will run the test script on an Ubuntu 22.04 environment. Make sure your script is compatible with this environment.
- If you are unable to run the test script locally, you can submit your solution and check the results on the Github.

## Resources

- Useful bash script examples: [https://linuxhint.com/30_bash_script_examples/](https://linuxhint.com/30_bash_script_examples/)
- Useful `jq` examples: [https://www.baeldung.com/linux/jq-command-json](https://www.baeldung.com/linux/jq-command-json)
- Use `jq` to create JSON: [https://spin.atomicobject.com/2021/06/08/jq-creating-updating-json/](https://spin.atomicobject.com/2021/06/08/jq-creating-updating-json/)

## Evaluation Criteria
Your submission will be evaluated based on:
- **Autograder**: Your code must pass the autograder [test script](./test/test.spec.ts).
- **Explainer Comments**: Include comments explaining each step of your code.
- **Code Quality**: Your code should be well-organized, commented, and adhere to best practices.

### Plagiarism Policy
Our plagiarism detection checker thoroughly identifies any instances of copying or cheating. Participants are required to publish their solutions in the designated repository, which is private and accessible only to the individual and the administrator. Solutions should not be shared publicly or with peers. In case of plagiarism, both parties involved will be directly disqualified to maintain fairness and integrity.

### AI Usage Disclaimer
You may use AI tools like ChatGPT to gather information and explore alternative approaches, but avoid relying solely on AI for complete solutions. Verify and validate any insights obtained and maintain a balance between AI assistance and independent problem-solving.

## Why These Restrictions?
These rules are designed to enhance your understanding of the technical aspects of Bitcoin. By completing this assignment, you gain practical experience with the technology that secures and maintains the trustlessness of Bitcoin. This challenge not only tests your ability to develop functional Bitcoin applications but also encourages deep engagement with the core elements of Bitcoin technology.