What is norecovery
this is when you are restoring a .bak but you plan on adding a differential backup on top, so you dont want the db to be live just yet. you might also add transaction logs on top of that.

it is the opposite of restoring with recovery which is just restoring straight up and making the db online.