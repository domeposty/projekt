# projekt
#VideoSegmenting - izreže testni video u manje segmente prema intervalima napisanim u times.txt fileu

#FacesFromVideo - iz jednog od izrezanih videa izdvojeni su frameovi te iz njih croppana lica i sejvana, zatim su ta lica pretvorena u np arrayeve i spremljena

#ModifiedFERdataset - FER2013 dataset je modificiran tako da postoje samo dva labela, expressionless i expressive, espressionless je neutral iz originalnog dataseta dok je expressive sve ostalo, slike i labeli su pretvoreni u np arrayeve i sejvani

#BuildingDataset - pomocu podataka iz ModifiedFERdataseta smo istrenirali CNN mrezu, val_loss=0.36, val_acc=0.83, zatim smo loadali podatke iz FacesFromVideo te predictali, dobivene vjerojatnosti smo sortirali te  *POKUSALI* pridruziti odgovarajuce np arrayeve (F) najvecoj i najmanjoj vjerojatnosti, np arrayevi bi zatim bili pretvoreni u slike i sejvani te taj proces bi se ponovio za svaki video sample dok ne izgradimo svoj dataset  
