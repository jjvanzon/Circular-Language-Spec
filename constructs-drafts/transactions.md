Circle Language | Construct Drafts
==================================

Transactions
------------

`[ Preliminary documentation ]`

While relational database are always transaction based, and you will never operate directly on the data, J Data by default operates directly on the data. In data, you do have the option to execute transactions. The adaptations to the data are then simply collected, until they are committed to the database. As data is queried for, the changes inside the transaction will be visible in it, even though the main data hasn’t been changed yet. This is simply done by checking the transactions every time a piece of data is shown and correcting the committed data that is displayed.

Transactions are stored in a data structure mainly as changes to literals / binary, additions of rows and removals of objects. Other types of changes may come to light as J Data 2 is developed.

