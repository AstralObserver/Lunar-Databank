The Johnny Decimal System (JDS) is a method of defining a [[Hierarchy]] for [[Sorting]]. It is typically used in relation to defining the structure of [[Folders]] in a system.

The goal of JDS is to create a hierarchy that will:
1. Avoid excessive depth of each topic
2. Promote easy standardized file-location and file-placement

# 1. Standard JDS Hierarchical Structure

It does this by defining a structure that uses a specific set of possible reference numbers (00.00 - 99.99) that defines an entire system structure. This structure is divided into labeled topics using a specific [[Place Value]] in the reference number. A reference number takes the format AC.ID and can be used to locate any designated folder in the entire structure. 

| Section       | Name         | Description                                         | Zero - Section        |
| ------------- | ------------ | --------------------------------------------------- | --------------------- |
| 00.00 - 99.99 | System       | An entire Johnny Decimal system for categorization. | JD Index (JDex)       |
| 10 - 90       | Area (A)     | The broadest possible topic.                        | System Management     |
| 1 - 9         | Category (C) | A subdivision of a Areas into more specific topics. | 'Area' Management     |
| .1 - .99      | ID           | The smallest division of a topic.                   | 'Category' Management |

This system for categorization prevents excessive sub-topic depth by limiting the structure to only 3 tiers. Finding where any one item is stored should thus take a maximum of 3 decisions to find where it is located. Furthermore, as each section corresponds to a number, a user can know directly where to look for the desired item if they use it's reference number. 

This means that a standard JDS will have:
- 9 Areas
- 81 Categories (9 Per Area)
- 7290 ID's (90 Per Category)

As each topic is labeled by it's number first, the file order will not change no matter the alphabetical or chronological order of it's label. In some cases, it might make more sense to replace the number value with a letter (A-Z) or date (Year/Month/Day) to encode useful data in the structure without needing to add additional metadata.

# 2. Standard JDS Zeros

JDS reserves the first 0-9 locations in each topic for specific functions. These sections are used for: partial-sorting when the specific location to place an item is unclear, can be defined in a more general way, or is useful when compiled from the sub-topics.

**JDS Standard Zeros**

| Index | Name                   | Description                                                                          |
| ----- | ---------------------- | ------------------------------------------------------------------------------------ |
| 00    | Index                  | Store information about the topic's definitions and structure.                       |
| 01    | Inbox                  | Temporary holding bin for items awaiting categorization.                             |
| 02    | Work In Progress       | Category level WIP folder to place in-progress documents pertaining to the category. |
| 03    | To-Do's and Checklists | For storing typical processes that relate to a specific topic.                       |
| 04    | URL's / Links          | For storing useful links related to a topic.                                         |
| 05    | Templates              | For storing template or template segments associated with this topic.                |
| 06    | Unused                 |                                                                                      |
| 07    | Unused                 |                                                                                      |
| 08    | Someday                | Long term holding bin for items awaiting categorization.                             |
| 09    | Archive                | Permanent uncategorized holding bin for items of this topic.                         |

# 3. Using JDS

## 3.1. Creating Your System

When adding defining a new topic, it is crucial to ensure there is no overlap between one topic or another. The standard rule of thumb is that the higher up a topic is on the hierarchy, the more general it is.

## 3.2. Adding or Retrieving Items

When placing an item one follows the same standard pattern:
1. If: Reference Number is pre-determined, place in path.
2. Else: Search for applicable Area in JDex or Structure
	1. If: None found, place in System Inbox
	2. Else: Search for applicable Category in JDex or Structure
		1. If: None found, place in 'Area' Inbox
		2. Else: Search for an applicable ID in JDex or Structure
			1. If: None found, place in 'Category' Inbox
			2. Else: Place in 'ID'

When retrieving an item, the process is identical with the only change being to "search for item in xxx" instead of "place in xxx".

___
References

Article - Johnnydecimal - Introduction
	Full documentation of the Johnny Decimal file system.
	https://johnnydecimal.com/10-19-concepts/11-core/11.01-introduction/

Repository - Github - index-spec
	Detailed specifications for a Johnny Decimal index file.
	https://github.com/johnnydecimal/index-spec

Post - Forum - Johnnydecimal - Alternative layout for the standard zeros
	A detailed changed layout that creates 9 categories and many additional ID's
	https://forum.johnnydecimal.com/t/the-standard-zeros/1558/11