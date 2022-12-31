---
title: abstractions
---

- Abstractions 
id:: c3951b52-582c-4a12-823e-28b0f6e0b294
	 - **An abstraction is a simplified view of an entity, which omits unimportant details. **
id:: dfdd72f9-e5de-4611-81f0-8382c2866fc0

	 - Abstractions are useful because they make it easier for us to think about and manipulate complex things. In [[modular design]] each module provides an abstraction for its [[The Module Interface]] the interface presents a simplified view of the module's functionality the details of the implementation are unimportant from the standpoint of the module's abstraction so they are omitted from the interface.
id:: 72f3648d-e15c-420a-a788-014e01431962

	 - the word "unimportant" is crucial. the more unimportant details that are omitted from an abstraction the better however a detail can only be omitted from an abstraction if it is unimportant. 
id:: 2c1b79e1-f768-48f7-88a5-804f4c03cedf

	 - An abstraction can go wrong in two ways. 
id:: 1dc2f3a6-5a2e-47f3-a2ec-0b37de4f6515
		 - First, it can include details that are not really important; when this happens it makes the abstraction more complicated than necessary, which increases the [[cognitive load]] on developers using the abstraction.
id:: 0ce714bc-44f2-4e47-8e34-69d851445f4b

		 - The second error is when an abstraction omits details that really important. This results in [[obscurity]] developers looking only at the abstraction will not have all the information they need to use the abstraction correctly. An abstraction that omits important details is a false abstraction it might appear simple, but in reality it isn't.
id:: 43936122-31f7-45ed-8ea9-ab7a16c99bee

	 - The key to designing abstraction is to understand what is important and to look for designs that minimize the amount of information that is important.
id:: 1f6c0972-1b9b-4705-97e7-78e12c2e5087

	 - We depend on abstractions to manage complexity not just in programming but pervasively in our everyday lives. Cars provide a simple abstractions that allows us to drive them without understanding the mechanisms for the engins tons of electronic stuff that is already inside. 
id:: 14c2f20e-69eb-4ca9-86d8-a7ceebc466f1
