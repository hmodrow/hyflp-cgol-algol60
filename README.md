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
	integer x,y;
	integer array prevGen[0:2,0:2], vecinos[0:2];
	prevGen := tablero;

	for i:=0 step 1 until 2 do
	begin
		for j:=0 step 1 until 2 do
		begin

		end;
	end

end;

procedure vecinos (tablero, x,y);
begin
	integer array vecinos[0:2];
	Boolean vecinoVivo;

	for i:=0 step 1 until 2 do
	begin
		for j:=0 step 1 until 2 do
		begin
			vecinoVivo := (abs(i-x) = 1) or (abs(i-x) = 1);
			if  vecinoVivo then
				begin
					if (tablero[i,j] == 1) then vecinos[i]:= 1
				end
		
		end;
	end
	

end;


inicializarTablero(tablero);
imprimirTablero(tablero);

end
