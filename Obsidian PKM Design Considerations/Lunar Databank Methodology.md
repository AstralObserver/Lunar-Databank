The [[Lunar Databank]] is intended to eventually be a unified cross-platform system for containing all of the information I learn and data I'd like to store. The long-term goal is to be able to safely move data from devices (iPhone, Laptop) with less powerful storage to those with more powerful storage (Desktop, Personal Server).

# 1. Initial Considerations

## 1.1. Initial Components
**Hardware**
- [[Melody's Desktop]]
- [[Melody's Laptop]]
- [[Melody's Phone]]

Software
- [[Windows Operating System]]: Primary OS of Melody's Desktop
- [[Linux Operating System]]: Primary OS of Laptop
- [[IPhone Operating System]]: Primary OS of IPhone
- [[Obsidian]]: Database Builder / Interface
- [[GitHub]]: Database Cross-Platform Syncing

## 1.2. Suspected Problems and Chosen Solutions
**Technology Problems**
- Problem One: Syncing is required between 3 different [[Operating Systems]].
	- Chosen Solution: Use the freeware application [[Obsidian]] for creating the database. This tool has a version for all 3 devices indicating it can store it's files in all 3 storage systems.  It also has a known paid syncing feature, but a requirement for this project is easily parse-able freeware. 

- Problem Two: Syncing on Obsidian natively requires a subscription.
	- Chosen Solution: Research found that there is a public [[Obsidian Syncing Addon]] that allows for the same ability by connecting to Obsidian on each device to one [[GitHub]] repository and allowing you to [[Push]] and [[Pull]] from the same branch from inside Obsidian.

- Problem Three: Syncing to IOS does not support certain features. (SSH, Size Limit, Rebase Merge Not Allowed, Submodules Not Supported).
	- Chosen Solution: There are two possible approaches that could resolve this issue. 
		- Connect Obsidian to iCloud and setting up iCloud on a computer. After this, it should be possible to collect [[Mercury Database]] changes from iCloud on a designated PC and push those changes to GitHub.
		- Send Messages from the iPhone to a email/texting service connected to a PC. Messages of this type are stored in a holding location on the [[Lunar Databank]] to manually sort and organize later.

**Organizational Problems**
- Problem One: The Lunar Databank must have a clearly defined structure methodology to improve upon later, but there are many methods to choose from that all may need adjustments.
	- Chosen Solution: Researched constructing a [[Personal Knowledge Management System]] to understand standard data structures and methodologies and develop the following system for organizing the data.


Assumptions: 
- A node can expand in these ways.
	- 1. When documenting, a page is created for a sub-document atomizing some sub-topic within the original page.
	- 2. When documenting, a parent page is created in order to detail a broader topic surrounding the subject. Making this article an atomized sub-document.
	- 3. When documenting, a topic is discovered that connects to a third already discussed topic. This non-sub non-super category of note is a bridge connection.
	- 4. When logging, a standardized page is created to fill a new node and append it to a connected area/list (reference, message, project, date, etc).

- I may want to navigate the data by.
	- Having a view for certain types of pages (Calendar for Dates)
	- Having certain screens designed to hold lists of ordered objects (Journal, Project Tasks)
	- Use tags associated with each Map of Contents (IE: Nonfiction.Genre1, Fiction.Genre2)
	- Use tags associated with any 'narrow-value'. Could be the title of a specific paper (to be indexed, could be the subject category. Level of specification is tied to the MOC that represents it. Lower tier MOC's should always be more specific)
	- Use a specific ID to instantly locate a node.
![InitialLunarDatabaseFileOrganization.excalidraw|width:100px](InitialLunarDatabaseFileOrganization.excalidraw.md)