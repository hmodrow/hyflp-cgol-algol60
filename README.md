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
		for j:=0 step 1 until 2 do
		begin
			printnln(tablero[i,j]);
		end
end;

inicializarTablero(tablero);
imprimirTablero(tablero);

end
