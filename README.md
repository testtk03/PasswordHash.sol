# PasswordHash.sol
Base - Smart Contract Deployed by Remix PasswordHash.sol
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract PasswordHash {
    bytes32 public hashedPassword;

    function setPassword(string memory _password) public {
        hashedPassword = keccak256(abi.encodePacked(_password));
    }

    function verifyPassword(string memory _password) public view returns (bool) {
        return hashedPassword == keccak256(abi.encodePacked(_password));
    }
}
