## Note that this code is for educational purposes and I will not be liable for any losses. You can contact a professional developer like me for a wholesome contract for business application.

Explanation:

rentNFT(uint256 tokenId, uint256 rentalPeriod, uint256 rentalPrice) external virtual

This function allows a user to rent an NFT by specifying the tokenId, rentalPeriod (in seconds), and rentalPrice in wei.
It checks that the rental period and price are valid and that the NFT is not already rented.
If the conditions are met, it sets the rental details in the rentals mapping and emits the NFTRented event.


approveRenter(uint256 tokenId, address renter) external virtual

This function allows the owner of an NFT to approve a specific address (renter) to rent their NFT.
It verifies that the sender is the owner of the NFT and that the NFT is available for rent.
If the conditions are met, it sets the approval status in the renterApprovals mapping and emits the RenterApproved event.


renterRental(uint256 tokenId) external payable virtual

This function allows a renter to rent an NFT by providing the tokenId and sending the required rental payment in wei.
It checks that the NFT is available for rent, not already rented, and that the renter is approved by the owner.
If the conditions are met and the rent payment is sufficient, it updates the rental details, transfers the payment to the NFT owner, and emits the NFTRented event.


returnNFT(uint256 tokenId) external virtual

This function allows the renter of an NFT to return it after the rental period has expired.
It checks that the NFT is available for rent, and only the renter can return it.
If the conditions are met, it marks the NFT as not rented by setting the renter address to zero and emits the NFTReturned event.


getRental(uint256 tokenId) external view virtual returns (address payable owner, address renter, uint256 rentalPeriod, uint256 rentalPrice, uint256 startDate, uint256 endDate, bool rented)

This function retrieves the rental details of an NFT identified by tokenId.
It returns the owner, renter, rental period, rental price, start date, end date, and rental status of the NFT.# NFT-rental
