https://github.com/Sri-Maniteja/srisblock.com/
![LOGO](web.png)
Developed by Sri Maniteja
github: https://github.com/Sri-Maniteja

 BlockAuthenticate represents a pioneering endeavor in blockchain-powered digital copyright protection. Users are empowered to upload their creative media files, affirming permanent ownership of their work. These uploaded works are made accessible for viewing by anyone on the web, with the added assurance of verifying the authenticity of the authorship. Moreover, the platform incorporates measures to prevent the uploading of content too closely resembling previously published works. Currently, BlockAuthenticate supports various file formats including audio, images, and text.
# Installing
**1st Run: Run the following commands from inside the project directory. The installation is going to take a few minutes to install all related packages in the virtual environment** 
```
source ./install.sh
python network.py
```
**Subsequent Runs:**
```
source ./run.sh
```
**We provides some example media files in media/ folder for you to test it out**

# How it Works
When a user uploads a file, a new block is appended to the blockchain. This block includes the title and creator of the work, a pathway or link for downloading the file, a hash derived from the file (to maintain manageable block sizes), the author's public key, a timestamp, and the hash of the preceding block. By utilizing the file's hash instead of its raw data, block sizes remain optimized. Including the author's public key enables ownership validation with the corresponding secret key. Additionally, the previous block's hash ensures the integrity of the blockchain by allowing users to confirm its untampered continuity.

# Media Comparison
To ensure the validity of a block, the uploaded content must differ significantly from any previously stored files on the chain. Perceptual hashing is employed for this comparison process. This hashing method generates concise fingerprints for files, where minor alterations to the file correspond to minor changes in the fingerprint. If the fingerprints demonstrate excessive similarity, it indicates that the files themselves are too alike. To generate these fingerprints, we utilize open-source software specifically designed for this task.
Audio comparison: [AcoustID](https://acoustid.org/)

Image comparison: [ImageMatch](https://github.com/EdjoLabs/image-match)

Text comparison: [TLSH](https://github.com/trendmicro/tlsh)

# Limitations
In practical terms, it's essential not to host the blockchain on a single server. The main benefit of blockchain is the absence of a centralized authority governing its contents. Achieving this requires extensive coding for networking and communication among worker nodes. Additionally, we haven't yet devised a method to thwart adversarial mining. While proof of work could be a solution, there's currently no incentive for successfully mining a block. If implemented, transaction fees would be necessary to motivate miners to publish blocks.

Another constraint arises as the blockchain expands, making it progressively challenging computationally to compare new fingerprints against the existing ones. Introducing probabilistically checkable proofs (PCPs) might offer a solution to accelerate the verification process. Scalability emerges as the primary obstacle should this project transition into real-world implementation.
# Vision
The BlockAuthentic initiative aims to establish a universally acknowledged platform for managing digital rights. It includes features like royalty management and dynamic tagging of web assets, fostering a more equitable and profitable environment for both content creators and users.

# Challenges
A significant hurdle for the project lies in establishing an effective method for verifying the uniqueness of digital assets. While the project employs media comparison libraries for this purpose, they come with inherent limitations. These limitations range from inconsistencies in accuracy to the challenge of defining an appropriate threshold for uniqueness. Additionally, the absence of a universal comparison library for all file types further complicates matters, as existing libraries are tailored to specific file formats.

# Takeaways
- Solving DRM is a complex challenge without a simple solution.
- Although blockchains could be utilized for identifying and protecting digital intellectual property, they have numerous limitations that may make them less than ideal.
- Digital media comparison is a nuanced and subjective area, necessitating further research and innovation to realize the vision of BlockAuthentic.
