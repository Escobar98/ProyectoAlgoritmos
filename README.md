# ProyectoAlgoritmos
Priorityqueue
//Juan quiere ordenar las calificaciones de su curso de mayor a menor promedio, Juan llevo 10 clases las cuales en su 
//boleta de calificacion estan oredenadas por orde alfabetico
//Ciencias naturales  95
//Ciencias sociales   85
//Civica  89
//Computacion 78
//Educacion fisica 93
//Español    90
//Ingles 81
//Matematicas   75
//Musica  79
//Religion  100
//Cree un programa utilizando el queue priority donde ordene las clases de mayor nota a menor nota.
 


package main

import pqueue "github.com/nu7hatch/gopqueue"

type Task struct {
	Name     string
	priority int
}

func (t *Task) Less(other interface{}) bool {
	return t.priority > other.(*Task).priority
}

func main() {
	q := pqueue.New(0)
	q.Enqueue(&Task{"ESPAÑOL=90", 90})
	q.Enqueue(&Task{"MATEMATICAS=75", 75})
	q.Enqueue(&Task{"CIENCIAS SOCIALES=85", 85})
	q.Enqueue(&Task{"CIENCIAS NATURALES=95", 95})
	q.Enqueue(&Task{"RELIGION=100", 100})
	q.Enqueue(&Task{"CIVICA=89", 89})
	q.Enqueue(&Task{"MUSICA=79", 79})
	q.Enqueue(&Task{"INGLES=81", 81})
	q.Enqueue(&Task{"EDUCACION FISICA=93", 93})
	q.Enqueue(&Task{"COMPUTACION=78", 78})
	println("juan quiere ordenar las calificaciones de su curso de mayor a menor calificacion, juan lleva 10 clases")

	for i := 0; i < 10; i += 1 {
		task := q.Dequeue()
		println(task.(*Task).Name)
	}
}
