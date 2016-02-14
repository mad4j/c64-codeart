c64-codeart
===========

Generate random patterns with Commodore 64.

```bas
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
240 DATA 024,024,028,239,247,056,024,024
250 DATA 024,024,056,247,239,028,024,024
```

![Screenshot](http://mad4j.github.io/c64-codeart/screenshot.png)

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

#### Make a click sound
```bas
POKE 54296,15:POKE 54296,0
```

#### Cheating quine
```bas
10 LIST
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

 #### Timing stuff
 Prints timer ticks since Power-On (1 Tick = 1/60 Second)
 ```bas
 PRINT TI
 ```
 
 Prints timer since Power-On in Hour/Minute/Second Format
 ```bas
 PRINT TI$
 ```
he accuracy of the timer is very poor (>1% drift)
