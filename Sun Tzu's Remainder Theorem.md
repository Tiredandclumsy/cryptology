Sun Tzu's Remainder Theorem (SRT), also commonly known as the Chinese Remainder Theorem (CRT), is a useful result in [[modular arithmetic]].
It states that given coprime $m,n \in \Bbb Z_{>1}$ and $a,b \in \Bbb Z$, $exists c,d \in \Bbb Z$ such that $cm + dn = 1$ and further $x = bcm + adn \pmod (mn)$ is the only number $\bmod mn$ such that $x \equiv a \bmod m$ and $x \equiv b \bmod n$
# Construction
The construction of the value $x$ can be attained by [[Euclid's Algorithm#Euclid's Corollary|Euclid's Corollary]], which states there exists some $c,d \in \Bbb Z$ such that $cm + dn = 1$, which is the first section of the theorem.
Now, consider $x = bcm + adn \pmod{mn}$. 
First, in the case $\bmod n$, $x = b(1-dn) + adn = b - bdn + adn \equiv b \pmod n$. 
Second, in the case $\bmod m$, $x = bcm + a(1-cm) = a - acm + bcm \equiv a \pmod m$.

#discrete-maths