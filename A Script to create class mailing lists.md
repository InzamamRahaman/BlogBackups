Piazza and Moodle are pretty neat digital classroom management tools. They allow discussions on material to transcend the classroom. They allow educators to host starter files and scripts their students might need for lab sessions. They allow students to upload their assignments, providing more comfort to frazzled students who might be worried about their lecturers receiving the work they have meticulously crafted or frantically rushed down. 

Piazza's and Moodle's spectrum of capacities can at times be too powerful a solution. You wouldn't use a broad sword to cut an apple, so when you need a simple solution for educator-student interaction, a traditional contact group can suffice. For the courses in which I tutor, I usually don't need to do anything more complex than distribute starter scripts. Consequently, I decided to just set-up a contact group and to distribute starter scripts that way.

Initially, I dreaded the thought of manually inserting 20+ students' contact information into a contact group, but then I remembered that I am a computer scientist. Why do something repetitive that I can make a machine do on my behalf! I wasn't familiar with the means of extending gmail, but I soon stumbled across Apps Script.

Apps Script is a JavaScript based scripting language that can be used to extend to functionality of Gmail and Google Docs. It can also be used to assemble gadgets to be placed on the Google Docs extension store. 

Now enlightened, I started hacking away with Apps Script, guided my its exquisite documentation. To create a contact list, I would need names and email addresses. I would also need to filter emails based on the subject that I instructed my students to use to request being added to the mailing list. To that end, I wrote the following script



