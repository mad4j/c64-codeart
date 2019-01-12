c64-codeart
===========

Generate random patterns with Commodore 64.

```basic
100 REM CODE-ART
110 REM DANIELE.OLMISANI@GMAIL.COM
120 PRINT "{CLEAR}"
130 REM PUT CHAR MAP AT 12288
140 POKE 53272, (PEEK(53272) AND 240)+12
150 REM DEFINE NEW CHARS
160 FOR K=0 TO 15
170  : READ A
180  : POKE 12288+K, A
190 NEXT K
200 REM DRAW RAND PATTERNS
210 PRINT CHR$(64.5+RND(1));
220 GOTO 210
230 REM CHARACTER DATA
240 DATA 016,016,032,192,003,004,008,008
250 DATA 008,008,004,003,192,032,016,016
```

![Screenshot](screenshot.png)

### Code Art

#### Hello World!
```bas
PRINT "HELLOWORLD!"
```

#### Random design
```bas
10 PRINT CHR$(205.5+RND(1)); : GOTO 10
```

#### Random music
```bas
10 POKE 54272+RND(1)*25,RND(1)*256 : GOTO 10
```

#### Is this a correct statement?
This is a correct statement but it returns the same message as `jfglajda`. So it is a correct statement or not?
```bas
PRINT "{DOWN}? SYNTAX ERROR";
```

The `{DOWN}` character is obtained by pressing the down cursor key

#### Make a click sound
```bas
POKE 54296,15:POKE 54296,0
```

#### Cheating quine
```bas
10 LIST
```

#### Actual quine
```bas
1 A$="1 A$=:PRINT LEFT$(A$,5)CHR$(34)A$CHR$(34)MID$(A$,6,49)":PRINT LEFT$(A$,5)CHR$(34)A$CHR$(34)MID$(A$,6,49)
```

**TBV**
```bas
10 READ A$:PRINT 10 A$:PRINT 20 "DATA" A$
20 DATA READ A$:PRINT 10 A$:PRINT 20 "DATA" A$
```


#### Computing PI
```bas
10 REM COMPUTING PI (NILAKANTHA SERIES) 
20 PRINT "{CLEAR}"
30 K=2: P=3: S=4
40 P=P+S/(K*(K+1)*(K+2))
50 PRINT "{HOME}";P
60 K=K+2: S=-S
70 GOTO 40
```

![Screenshot](pi.png)


Otherwise, by cheating
```bas
PRINT {PI}
```

#### Hofstadter Q sequence

```bas
100 REM HOFSTADTER Q NUMBERS
110 DIM Q(1000)
120 Q(1)=1 : Q(2)=1
130 FOR N=3 TO 1000
140 : Q(N) = Q(N-Q(N-1)) + Q(N-Q(N-2))
150 NEXT N
160 PRINT "FIRST NUMBERS: ";
170 FOR I=1 TO 10
180 : PRINT Q(I);
190 NEXT I
200 PRINT
210 PRINT "1000th NUMBER: "; Q(1000)
```

#### Fibonacci Numbers
```bas
10 REM FIBONACCI NUMNBERS
20 A=1: B=1
30 PRINT A; B;
40 FOR I=3 TO 15
50 T=A+B: A=B: B=T
60 PRINT T;
70 NEXT
```

#### Memory Worm
```bas
10 POKE RND(1)*65536, RND(1)*256 : GOTO 10
```

#### Random stuff
```bas
10 P=RND(1)*1000 : POKE 1024+P, RND(1)*128 : POKE 55296+P, RND(1)*16 : GOTO 10
```

#### Timing stuff
Prints timer ticks since Power-On (1 Tick = 1/60 Second)
```bas
PRINT TIME
```
 
Prints timer since Power-On in Hour/Minute/Second Format
```bas
PRINT TIME$
```
The accuracy of the timer is very poor (>1% drift)

#### Soft reset
```bas
SYS 64738
```


