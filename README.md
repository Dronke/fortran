character text*70
integer i, l, k
write(*,*) 'vvedite text'
read(*,'(A70)') text
l=LEN(text)
k=0
do i=1,l
if (text(i:i)==' ') then
k=k+1
end if
end do
k=k+1
dimension a(k)
character a
a(1)=text(1:1)
n=1
do m=1,k
do i=n,l
if (text(i+1:i+1)=' ') then
a(m)=text(n:i)
n=i+2
exit
end if
end do
end do
do while (P)
h=0
do m=1,k
l1=LEN(a(m))
l2=LEN(a(m+1))
if (l1>l2) then
buf=a(m)
a(m)=a(m+1)
a(m+1)=buf
h=h+1
end if
end do
if (h=0) then
P=.false.
end if
end do
write(*,*) a
end
