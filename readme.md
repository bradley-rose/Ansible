# Network Engineer Basics to Ansible
Ansible has been popping up everywhere, and I could not, for the life of me, understand a) how to use it, and b) why to use it. I'm starting to see it's purpose now.

For bulk network appliance management, Fortinet makes FortiManagers, Palo Alto makes PANOs, etc. But those are vendor proprietary and **bloody** expensive. Also, they don't come with documented version control built-in like Git does. Git and Ansible are both free, and arguably better SO LONG AS you don't mind working with the CLI in place of the GUI. This is far more extensible, sharable, etc. It's just controlled by two key components: SSH connections to the target devices, and file permissions on your Ansible directory, making this more secure than having an expensive system requiring expensive support contracts to keep updated and away from vulnerabilities. 

This is a very, very basic setup for setting up Ansible, and so far I have it configured to work with two FortiGate devices in a local Eve-NG environment.Clone the configuration to anywhere on your local machine (and make sure you have the Ansible binaries installed), change the host variables to point to your own devices, and you should be able to get it working in no time. 

## Note
There is a chance you might have to install certain "modules" for different types of devices, known as collections. For example, I'm not sure if this was required, but if you're having trouble with getting the ASA modules to work: 

`ansible-galaxy collection install fortinet.fortios`.

## Update
I feel obligated to comment on my learning patterns here. At present date, Ansible is thrown around as this ubiquitous tool that can automate anything and everything. It's easy, you don't have to learn how to program, you just have to learn it's proprietary methods to get automation integrated in your environment. All I have to say is: Ansible can be convoluted. I've programmed before, and I'm very used to how programming languages work. For this reason alone, Ansible was unbelievably unintuitive for me, and I hugely prefer programming directly in a programming language that gives me all of the control back.

I didn't really understand how to work with REST APIs at the time. I've learned a bit more about them, and you can see those results in action with the Fortinet API [listed at this repository](https://github.com/bradley-rose/pyFortinetAPI). Someone had begun developing Python modules for many available API calls. I have custom developed more actions here, and I can manipulate the inputs and outputs this way with much more ease than I found was possible with Ansible. **This is not to steer you away from Ansible!** If it works for you, and you can understand it's logic with YAML, it's a very powerful tool: it's idempotent, it gives a nice, colour-coded recap after runtime, etc. I only state this to inform you that: 

a) There are alternatives and multiple methods to getting a job done (Python is quicker than Ansible, and more customizable, but the learning curve for those of you who don't have experience programming may be steeper); and  
b) You may prefer one or the other depending on your experience with programming. 

Have fun, I hope this works well for you!