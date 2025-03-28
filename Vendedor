#include <stdio.h>

int main() {
    int id, stock = 0, cantidad, opc;
    float precio = 0, total_ganancias = 0, venta, precio_d, descuento=0;
    char nombre[30];

    do {
        printf("\nMenú de Opciones:\n");
        printf("1. Ingresar el producto\n");
        printf("2. Vender producto\n");
        printf("3. Reabastecer producto\n");
        printf("4. Mostrar información del producto\n");
        printf("5. Mostrar total de ganancias\n");
        printf("6. Salir\n");
        printf("Seleccione una opción: ");
        scanf("%d", &opc); // el & simpre se pone menos en el fgets


        switch(opc) {
            case 1:
                printf("Ingrese el ID del producto: ");
                scanf("%d", &id);

                printf("Ingrese el nombre del producto: ");
                fflush(stdin);//limpia el cache
                fgets(nombre, 30, stdin); //fgets lee cadenas y el stdin entrada estandar lee espacios no como scanf que no los lee
            do {
                    printf("Ingrese el stock: ");
                    scanf("%d", &stock);
                    printf("Ingrese el precio unitario del producto: ");
                    scanf("%f", &precio);
                    if (stock <= 0 || precio <=0) {
                        printf("Ninguno de los dos valores puede ser 0 o negativo, intente denuevo.\n");
                    }
                } while (stock < 0 || precio <=0);
         
                break;

            case 2:
            if (stock <= 0) {
                    printf("No hay stock para vender\n");
                    break;
                }
                do {
                    printf("Ingrese la cantidad a vender: ");
                    scanf("%d", &cantidad);
                    if ( cantidad <=0) {
                        printf("Debe vender minimo una unidad, tampoco se perimiten numeros negativos\n");
                    } 
                    if (cantidad > stock) {
                        printf("Stock insuficiente\n");
                    }
                } while (cantidad < 1 || cantidad > stock);
                 do {
                    printf("Ingrese el porcentaje de descuento:");
                    scanf("%f", &descuento);
                    if (descuento < 0 || descuento > 100) {
                        printf("El descuento debe ser de 0 a 100.\n");
                    }
                } while (descuento < 0 || descuento > 100);
                
                precio_d = precio - (precio * descuento / 100);
                venta = cantidad * precio_d;
                printf("el precio de venta es de:%.2f\n",venta);
                total_ganancias += venta; // += va acumulando la varibale QUE ESTA en la DERECHA - DENTRO de la variable que esta a la IZQUIERDA
                stock-=cantidad; ; // -= va restando la varibale QUE ESTA en la DERECHA - DENTRO de la variable que esta a la IZQUIERDA
                printf("el nuevo stock es: %d\n", stock);
                break;

            case 3:
                cantidad=0;
                    printf("Ingrese la cantidad a agregar al stock: ");
                    scanf("%d", &cantidad);
                    do {
                        printf("Agrege minimo una unidad.\n");
                        printf("Ingrese la cantidad a agregar al stock: ");
                    scanf("%d", &cantidad);
                    } while (cantidad <= 0); 
                stock += cantidad;
                printf("Stock actualizado. Nuevo stock: %d\n", stock);
                break;

            case 4:
                printf("\nInformación del producto:\n");
                printf("ID: %d\n", id);
                printf("Nombre: %s\n", nombre);
                printf("Stock disponible: %d\n", stock);
                printf("Precio unitario: $%.2f\n", precio);
                break;

            case 5:
                printf("Total de ganancias acumuladas: $%.2f\n", total_ganancias);
                break;

            case 6:
                printf("Saliendo del programa...\n");
                break;

            default:
                printf("Intente nuevamente.\n");
                break;
        }
    } while (opc != 6);

    return 0;
}
