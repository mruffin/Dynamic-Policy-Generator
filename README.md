<style>h1 { border-bottom: 0; } </style>

# <h1 align="center"> Dynamic Policy Generation Tool

## <h2 align="center"> 🛑 Stop Please Read 🛑 <br> 🚧 This Repositry is currently under construction. 🚧 <br> Please check back later to find updated usage instructions and working code for reproducibility. 

## Remote Attestation
**Remote Attestation** is designed to prove a property of a system to a third party, which in this case, is you. It can provide proof that the execution environment can be trusted before beginning to execute code or before proceeding to deliver any secret information. Remote attestation can provide different services, such as measured boot attestation and runtime integrity monitoring, using a hardware-based cryptographic root of trust, otherwise known as a Trusted Platform Module (TPM).

<div align="center">
<img  src="images/keylime.png" alt="Remote Attestation Diagram" width="75" height="75">
<h2 style="text-align:center;  border-bottom: 0; margin-top:-1px;"> Keylime

</div>

If you want to **continuously** make sure that things aren’t being altered in real-time you can use Linux kernel's Integrity Measurement Architecture (IMA) with runtime integrity monitoring. The tools in this repository can help you do that. These tools are designed to work with [Keylime](https://keylime.dev/), a highly scalable remote boot attestation and runtime integrity measurement solution.


## Tools Breakdown
In this repository, you will find various tools to help you generate runtime policies for **continuous** integrity monitoring with Keylime, parse through errors in the Keylime Verfier, and more. 

#### Runtime Policy Generation
##### Generating a New Policy
To create a new runtime policy, run the following command. Run command -h to see the help menu. <br>
<code>python3 runtime_update_allowlist.py -x -v jammy -g -e </code>

##### Updating an Old Policy
To update an existing runtime policy that is on your local machine, run the following command. Run command -h to see the help menu. <br>
<code>python3 runtime_update_allowlist.py -x -v jammy -u -e </code>
_________________
#### Keylime Verifier Log Parser
To parse through the Keylime Verifier Log and retrieve all the errors run the following command: <br>
<code> python3 parse_verifier.py -f /path/to/verifier.txt -o /path/to/output/file.txt -e </code>

Note: Change the -e to -a to keep all lines in the log but in a more readable format. <br>
