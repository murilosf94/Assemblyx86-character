.model small
.data
    msg db 'Digite um caractere: $'
    msg1 db 13,10, 'O caractere digitado e uma letra minuscula!!! $'
    msg2 db 13,10, 'O caractere digitado e um numero!!! $'
    msg3 db 13,10, 'O caractere digitado e desconhecido!!! $'
    msg4 db 13,10, 'O caractere digitado e uma letra maiuscula!!! $'
.code
    main proc
        mov ax, @data
        mov ds, ax

        ;ler a primeira mensagem
        mov ah, 09
        lea dx, msg
        int 21h

        ;digitar o caractere
        mov ah, 01
        int 21h
        mov bl, al

        ;comparar o caractere digitado para ver se é número
        cmp bl, 30h
        jb naonumero
        cmp bl, 39h
        ja naonumero
        ;se chegou ate aqui é numero e da um jump para numero
        jb numero

        numero:
            ;é numero, entao da um jump para o numero1
            jmp numero1
        naonumero:
            ;um jump p continuar
            jmp continua


        continua:
            ;comparar o caractere digitado para ver se é letra minuscula
            cmp bl, 61h
            jb naoletramin
            cmp bl, 7ah
            ja naoletramin
            ;se chegou ate aqui é letra minuscula e da um jump para letramin
            jb letramin

        letramin:
            ;é letra minuscula, entao da um jump para o letramin1
            jmp letramin1
        
        naoletramin:
            ;um jump p continuar
            jmp continua1

        continua1:
            ;comparar o caractere digitado para ver se é letra maiuscula
            cmp bl, 41h
            jb naoletramai
            cmp bl, 5ah
            ja naoletramai
            ;se chegou ate aqui é letra maiuscula e da um jump para letramai
            jb letramai

        letramai: 
            ;é letra maiuscula, entao da um jump para o letramai1
            jmp letramai1

        naoletramai:
            ;se chegou ate aqui é desconhecido, entao da um jump para desconhecido
            jmp desconhecido

        
        numero1:
            mov ah, 09
            lea dx, msg2
            int 21h
            ;jump para o fim do codigo
            jmp fim
        
        letramin1:
            mov ah, 09
            lea dx, msg1
            int 21h
            ;jump para o fim do codigo
            jmp fim

        letramai1:
            mov ah, 09
            lea dx, msg4
            int 21h
            ;jump para o fim do codigo
            jmp fim
        
        desconhecido:
            mov ah, 09
            lea dx, msg3
            int 21h
            ;jump para o fim do codigo
            jmp fim

        ;fim do codigo
        fim:
            mov ah, 4ch
            int 21h
    
    main endp
    end main
