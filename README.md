# Desafio Dio Modificando um Microgame com Unity



**Código Completo e Abrangente para Modificando um Microgame com Unity**



Os microgames são uma ótima maneira de começar a usar o Unity. Eles são pequenos jogos que podem ser criados em pouco tempo e são uma ótima maneira de aprender os fundamentos do desenvolvimento de jogos.



### **Passo a Passo**

### **1. Crie um novo projeto no Unity**

Abra o Unity e clique em "Novo Projeto". Digite um nome para o seu projeto e selecione um local para salvá-lo.



### **2. Importe o pacote de microgames**

Vá para a Asset Store e pesquise por "Microgames". Importe o pacote para o seu projeto.



### **3. Crie uma nova cena**

Clique em "Arquivo" > "Novo" > "Cena". Isso criará uma nova cena no seu projeto.



### **4. Adicione um objeto de câmera à cena**

Arraste e solte um objeto de câmera da hierarquia para a cena. Isso criará uma câmera que renderizará a cena.



### **5. Adicione um objeto de jogador à cena**

Arraste e solte um objeto de jogador da hierarquia para a cena. Isso criará um jogador que você poderá controlar no jogo.



### **6. Adicione um script ao objeto do jogador**

Clique duas vezes no objeto do jogador na hierarquia para abrir o inspetor. Clique em "Adicionar Componente" e adicione o script "MicrogameController".



### **7. Configure o script do controlador de microgame**

No inspetor, defina as seguintes propriedades do script do controlador de microgame:



- **Velocidade do jogador:** A velocidade do jogador no jogo.
- **Velocidade do projétil:** A velocidade dos projéteis disparados pelo jogador.
- **Tempo de vida do projétil:** O tempo que os projéteis permanecem na cena antes de serem destruídos.



### **8. Teste o jogo**

Clique no botão "Play" na barra de ferramentas para testar o jogo. Você deve ser capaz de controlar o jogador e disparar projéteis.



### **Código do Script MicrogameController**

csharp



```csharp
using UnityEngine;

public class MicrogameController : MonoBehaviour
{
    public float playerSpeed;
    public float projectileSpeed;
    public float projectileLifetime;

    private Rigidbody2D playerRigidbody;

    private void Start()
    {
        playerRigidbody = GetComponent<Rigidbody2D>();
    }

    private void Update()
    {
        // Movimento do jogador
        float horizontalInput = Input.GetAxis("Horizontal");
        float verticalInput = Input.GetAxis("Vertical");

        playerRigidbody.velocity = new Vector2(horizontalInput * playerSpeed, verticalInput * playerSpeed);

        // Disparo de projéteis
        if (Input.GetButtonDown("Fire1"))
        {
            GameObject projectile = Instantiate(Resources.Load("Projectile") as GameObject, transform.position, Quaternion.identity);
            projectile.GetComponent<Rigidbody2D>().velocity = transform.up * projectileSpeed;
            Destroy(projectile, projectileLifetime);
        }
    }
}
```



## **Conclusão**



Este é um guia básico sobre como criar um microgame com Unity. Você pode personalizar o jogo adicionando seus próprios gráficos, sons e jogabilidade.
