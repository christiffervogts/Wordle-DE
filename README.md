# Wordle-DE
This is a wordle created for the German language. Meant to be used in German classes or for fun.

**BEFORE YOU CAN USE THIS GO [HERE](https://download.eclipse.org/justj/jres/22/downloads/latest/) AND DOWNLOAD YOUR JRE 22 THEN PUT IT IN THE FILE WITH YOUR STUFF. IF THE JRE IS NOT 22 THEN THERE IS NO GERENTEE THAT IT WILL RUN.**
**IF THAT LINK DOES NOT WORK LOOKUP Eclipse JustJ and download your JRE that is 22+**
1) Use Case
   This is created for fun in a class or just for fun. In my German classes in High School I played a German Wordle on the borad and wanted to make a mechanical version of this for people to use in other classes. 
3) What Makes it German?
   The only reason this is called Wordle - DE is because it supports german keyborads and has a german word bank. This ofcourse means that you need a german keyborad to play as some words contain umlauts and eszetts. 
5) How to mod for other languages?
   If you want to mod this for other languages then that's super easy! useing something like winrar open the body file from the JAR (you may have to remake the exicutible, I reccomend launch4j as that's what I use and I include the .xml file for your convinience). Just replace the bank.txt file with your own bank. **The delimiter must be makeing a new line or it will not work!** and if your language more letters you can alter the Array titles letters in the startup function. currently it looks like:

   		 String[] letters = {
		            "Q", "W", "E", "R", "T", "Z", "U", "I", "O", "P", "Ü",
		              "A", "S", "D", "F", "G", "H", "J", "K", "L", "Ö", "Ä",
		                "Y", "X", "C", "V", "B", "N", "M", "\u00DF", "DELETE", "ENTER"
		        };
   
but if I were to alter this for spanish I would change this to Ñ

   		 String[] letters = {
		            "Q", "W", "E", "R", "T", "Y", "U", "I", "O", "P",
		              "A", "S", "D", "F", "G", "H", "J", "K", "L", "Ñ",
		                "Z", "X", "C", "V", "B", "N", "M", "DELETE", "ENTER"
		        };
Then this would require me to go and edit the first For loop. to chage it from 

		            for (int i = 0; i < letter.length; i++) {
		            letter[i] = new JButton(letters[i]);
		            letter[i].setBounds(x, y, 45, 45);
		            letter[i].addActionListener(this);
		            frame.add(letter[i]);
                
                x += 50;
                
		            if (i == 10) { 
		                x = 30;
		                x+=15;
		                y += 50;
		            }
		            if (i == 20) {
		            	x = 30;
		                x+=40;
		                y += 50;
		            }
		            if(i == letter.length-2) {
		                y += 50;
		            	x = 30;
		                x+=40;
		            	letter[i].setBounds(x,y,195, 45);
		            }
		            if(i == letter.length-1) {
		            	x += 150+50;
		            	letter[i].setBounds(x,y,195, 45);
		            }

		         }
             
and we only need alter the if (i == 10), if ( i == 20) to their correct lengths. 
