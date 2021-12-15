1. ERC20Tempo deployment
2. sTempoERC20 deployment
3. TempoBondingCalculator(ERC20Tempo address) deployment
4. Treasury(ERC20Tempo address, MIM address, 0) deployment

5. ERC20Tempo ----> setVault(Treasury address)
6. Staking(ERC20Tempo address, sTempoERC20 address, 28800, 0, block.timestamp(ofLaunch) + 28800) deployment
7. sTempoERC20 -----> initialaze(staking address)
8. StakingWarmup(Staking address, sTempo address) deployment
9. StakingDistributor(Treasury address, ERC20Tempo address, 28800, block.timestamp(ofLaunch) + 28800) deployment
10. StakingDistributor ----> addRecipient(Staking address, 5000);
11. Staking ------> SetContract(0, StakingDistributor address)
12. Staking ------> SetContract(1, StakingWarmup address)
13. StakingHelper(ERC20Tempo address, Staking address) deployment

14. ETHTimeBondDepository(TEMPOERC20 address, Wavax address, Treasury address, multisigWallet address,0x0A77230d17318075983913bC2145DB16C7366156) deployment
15. ETHTimeBondDepository ----> initializeBondTerms(5, 17000, 1000, 1000000000000000000000000, 0,432000)
16. ETHTimeBondDepository ----> setStaking(stakingHelper address, 1)

17. TempoBondDepository(TEMPOERC20 address, MIM address, Treasury address, multisigWallet address, 0) deployment
18. TempoBondDepository ----> initializeBondTerms(5, 8000, 1000, 10000, 1000000000000000000000000, 0,432000)
19. TempoBondDepository ----> setStaking(stakingHelper address, 1)

20. LPTempoBondDepository(TEMPOERC20 address, JoePair address, Treasury address, multisigWallet address, bondCalculator address) deployment
21. LPTempoBondDepository ----> initializeBondTerms(5, 1075, 1000, 0, 1000000000000000000000000, 0,432000)
22. LPTempoBondDepository ----> setStaking(stakingHelper address, 1)

Treasury
QUEUE ---> Toggle
{
    0: FortBondDepository  owner
    2: Wavax 0xB31f66AA3C1e785363F0875A1B74E27b85FD66c7
    3: owner
    4: owner LPFortBondDepository
    5: JoePair
    8: AVAXFortBondDepository Distributor
}
