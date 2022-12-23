# Differential equations with parameters


```
def f(t,y,h):
    return y*(1-y) - h

t0 = 0
tmax = 10
ic = [0.4]

hvals = [0, 0.15, 0.25, 0.4]
labels = ['$h=0$', '$0<h<1/4$', '$h=1/4$', '$h>1/4$']

for k in range(4):
    soln = solve_ivp( f, [t0,tmax],ic, args=[hvals[k]], t_eval=np.linspace(t0,tmax, 1000) )
    plt.plot(soln.t, soln.y[0], label=labels[k])

    
plt.legend(title='harvesting')

plt.ylim(0, 1.1)

xplus = 0.5 + np.sqrt(0.25 - hvals[1])
xminus = 0.5 - np.sqrt(0.25 - hvals[1])
plt.yticks([0,xminus, 0.5, xplus,1], [0, '$x_-$', 0.5,'$x_+$', 1])

plt.title('Simple logistic model with harvesting')
plt.xlabel('time $t$')
plt.ylabel('percent habitat occupied')
plt.show()
```