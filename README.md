# Pet Park

## Goal

The goal of this exercise is to develop a pet park smart contract. The basic structure of this contract has been laid out for you in `src/PetPark.sol`. We can have 5 kinds of animals in our pet park

-   Fish (AnimalType: 1)
-   Cat (AnimalType: 2)
-   Dog (AnimalType: 3)
-   Rabbit (AnimalType: 4)
-   Parrot (AnimalType: 5)

To install foundry refer to the document [here](https://book.getfoundry.sh/getting-started/installation).

This assignment is divided into two parts. In `Part A` of the assignment you need to write the unimplemented `PetPark` contract. In `Part B` of the assignment we have a few incomplete tests you need to complete in `test/PetPark.t.sol`.

### Part A

Complete this contract with following specifications for each function

-   add

    -   Takes `Animal Type` and `Count`. Gives shelter to animals in our park.
    -   Only contract owner (address deploying the contract) should have access to this functionality.
    -   Emit event `Added` with parameters `Animal Type` and `Animal Count`.

-   borrow

    -   Takes `Age`, `Gender` and `Animal Type`.
    -   Can borrow only one animal at a time. Use function `giveBackAnimal` to borrow another animal.
    -   Men can borrow only `Dog` and `Fish`.
    -   Women can borrow every kind, but women aged under 40 are not allowed to borrow a `Cat`.
    -   Throw an error if an address has called this function before using other values for `Gender` and `Age`.
    -   Emit event `Borrowed` with parameter `Animal Type`.

-   giveBackAnimal
    -   Throw an error if user hasn't borrowed before.
    -   Emit event `Returned` with parameter `Animal Type`.

### Part B

Complete the following tests in `test/PetPark.t.sol`

-   `testCannotAddAnimalWhenNonOwner`
    -   Test that any non-owner account cannot add animals using the `add` function

-   `testCannotBorrowWhenAgeZero`
    -   Test that the borrow function fails when called with an age equal to 0.

-   `testBorrowCountDecrement`
    -   Test that the count of animal decreases correctly when the `borrow` function is called.

## Evaluation

-   Clone this template repo, by clicking on `Use this template` and then selecting `Create a new repository`

-   Give a name to this repo and set visibility to `Private`

-   Add us as collaborators
    - Go to the `Settings` tab
    - Select `Collaborators` from the left pane
    - Click `Add People`
    - Add username `shubham-kanodia` as a collaborator

-   Clone the repo you just created. Use the flag `--recurse-submodules` to clone the forked repo along with the submodules. You can use the following command after replacing the `CLONE_URL` with the clone url of your repo

    ```
    git clone --recurse-submodules CLONE_URL
    ```

-   Install `forge-std` library using the below command
    ```
    forge install foundry-rs/forge-std --no-commit
    ```

-   Make changes to the `src/PetPark.sol` file. The tests in `test/PetPark.t.sol` should run successfully.

-   Run Tests
    ```
    forge test
    ```

-   Push your changes to `main` branch of your repo to trigger the GitHub workflow that runs these tests.

-   Submit your name, email and link to your forked repo [here](https://airtable.com/apppwJwKgRGomJLLY/shrhkY0IVT8zxiM0Z).

## Note

-   The error strings (mentioned in the revert statement) must be the same as the ones mentioned in tests.
-   Use modifiers and structs where appropriate.

## Reference

- [Foundry Book](https://book.getfoundry.sh/getting-started/first-steps)
