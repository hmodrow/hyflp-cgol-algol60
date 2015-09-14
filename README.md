# hyflp-cgol-algol60
Conway's game of life in ALGOL60
begin 

integer i,j;
integer array tablero[0:2,0:2];

procedure inicializarTablero (tablero);
begin
	for i:=0 step 1 until 2 do
		for j:=0 step 1 until 2 do
			begin
				if (i != j) then
					 tablero[i,j]:= 0
				else
				 	tablero[i,j]:=1;
				
			end

end;

procedure imprimirTablero (tablero);
begin
	for i:=0 step 1 until 2 do
	begin
		for j:=0 step 1 until 2 do
		begin
			printn(tablero[i,j]);
		end;
		printsln(`');
	end
end;		


procedure aplicarReglas (tablero);
begin
	integer vecinos,actual;
	integer array prevGen[0:2,0:2];
	copiarTablero(prevGen,tablero);

	for i:=0 step 1 until 2 do
	begin
		for j:=0 step 1 until 2 do
		begin
			actual := prevGen[i,j];
			contarVecinosVivos (prevGen,i,j,vecinos);
			if (actual = 1) then
			begin
				if (vecinos < 2) then
					 tablero[i,j]:=0 
				else
					if (vecinos <= 3) then
						tablero[i,j]:=1
					else 
						tablero[i,j]:=0;				
			end
			else
				if (vecinos = 3) then tablero[i,j]:=1;
				
		end;
	end

end;

procedure contarVecinosVivos (tablero, x,y, vecinos);
begin
	Boolean esVecino;
	vecinos := 0;
	for i:=0 step 1 until 2 do
	begin
		for j:=0 step 1 until 2 do
		begin
			esVecino := (abs(i-x) = 1) | (abs(j-y) = 1);
			if  esVecino then
				begin
					if (tablero[i,j] = 1) then vecinos := vecinos +1
				end
		
		end;
	end
	

end;

procedure copiarTablero (prevGen,tablero);
begin
	integer i,j;
	for i:=0 step 1 until 2 do
		for j:=0 step 1 until 2 do
			prevGen[i,j]:= tablero[i,j];

end;

inicializarTablero(tablero);
aplicarReglas(tablero);
imprimirTablero(tablero);

end
