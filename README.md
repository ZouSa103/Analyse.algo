program InsertionSort;

const
  maxSize = 50;

type
  IntArray = array[1..maxSize] of Integer;

var
  arr: IntArray;
  n, i, j, key: Integer;

procedure InsertionSort(var arr: IntArray; n: Integer);
begin
  for i := 2 to n do
  begin
    key := arr[i];
    j := i - 1;

    while (j >= 1) and (arr[j] > key) do
    begin
      arr[j + 1] := arr[j];
      j := j - 1;
    end;

    arr[j + 1] := key;
  end;
end;

begin
  Write('Enter the number of elements: ');
  ReadLn(n);

  WriteLn('Enter the elements:');
  for i := 1 to n do
    Read(arr[i]);

  InsertionSort(arr, n);

  WriteLn('Sorted array:');
  for i := 1 to n do
    Write(arr[i], ' ');
end.
