# Note
This is a tool for writing, restoring and retriving notes in command line. Here are some examples of command:


1. **note add [note.txt]**   
   create a template note text file in the current directory with a default name 'note.txt'
2. **note save note.txt**  
   save the the note in the file of 'note.txt'
3. **note get keyword0 [keyword1 ... keywordN]**  
   the note about the keyword(s) will be printed in the terminal
4. **note change note.txt**  
if you want to change the content for a special note, you can firstly output the note to a file(`note get keyword0 keyword1 ... keywordN > note.txt `), then change the file, and save the change lastly.(If the file is empty the note will be deleted)

# Implementation
For each note, it has two components which are keyword(s) and content.
In order to save the notes, a database is created. The database has two tables. One table is a dict, whose keys and values are the keywords and the note ids. Each id links to a note. The other table has three columns: the notes' ids, the keywords which the notes linked to, the note contents.

```
create table keywords (
  keyword string primary key not null,
  ids string not null
);

create table notes (
  id integer primary key autoincrement,
  keywords string not null,
  content string not null
);
```

# to do
1. get notes with bool filter
2. suppert a gui
