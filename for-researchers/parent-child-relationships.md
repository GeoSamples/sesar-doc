# Parent-child Relationships

### **Children Samples - Hierarchical Sample Relationships**

Many objects that are sampled from the Earth yield subsamples. For example, sediment cores may be sampled at regular intervals, creating hundreds of individual samples from one core. This relation among samples is considered a parent-child relationship in the world of data management: sub-samples are children of a parent sample. Subsamples can be sampled themselves, leading to complex hierarchies.&#x20;

SESAR has been designed to record the relationship between samples and sub-samples. Subsamples have their own entry in SESAR and have independent IGSNs. The parent-child relationship is established by recording the IGSN of the parent in the child metadata profile. A parent sample must be registered with an IGSN before it can be listed as the parent of any child samples.

By adding a ‘Parent IGSN’ to a sample, the metadata profile page of the newly registered sample will show that it is a sub-sample of the sample that was listed in the ‘Parent IGSN’ field. The metadata profile page will also show all other samples (siblings) that share the sample parent. The metadata profile page of the sample whose IGSN was listed in the ‘Parent IGSN’ of the newly registered sample will also show that the newly registered sample is a sub-sample (child) of it.&#x20;

### Minting Children Samples and IGSNs

Now you can mint child IGSNs directly from a registered sample.

1. In your sample management page within your personal, team, and group samples, select the sample you want to mint a child from.
2. Click ‘Mint Child’.
3. A popup page with the parent IGSN’s pre-populated metadata fields will show up. You can choose which fields you want to maintain and keep for the child sample.&#x20;
4. Click ‘Continue to registration’ which will prompt you to the ‘Register a child sample’ page.&#x20;
5. Follow the steps to register your child. This process is the same as the individual registration process.&#x20;
6. Once you submit, the child sample will be sent to the SESAR curator for review. Until it is approved, your sample will be labeled ‘pending’.&#x20;

<img src=".gitbook/assets/unknown (15).png" alt="" height="539" width="624">

<br>
