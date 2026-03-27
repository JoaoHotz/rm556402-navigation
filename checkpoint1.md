
# Checkpoint01 - explicação dos commits

## Descriçao do Projeto:

O projeto consiste no desenvolvimento de uma aplicação Android utilizando Kotlin e Jetpack Compose, com foco na criação de uma interface moderna e na implementação de múltiplas telas. A aplicação permite a navegação entre diferentes telas, simulando um fluxo de interação do usuário dentro do aplicativo.

Durante o desenvolvimento, foram criadas telas independentes com responsabilidades específicas, conectadas por meio do Navigation Compose, permitindo uma navegação fluida. Além disso, o projeto implementa a passagem de parâmetros entre telas, possibilitando que dados inseridos em uma tela sejam utilizados em outra, tornando a aplicação mais dinâmica e interativa.

## Objetivo da prova:

O objetivo do checkpoint é avaliar a capacidade do aluno de implementar navegação entre telas em uma aplicação Android utilizando o Navigation Compose, além de demonstrar o entendimento do fluxo de navegação e da comunicação entre diferentes partes do sistema.

A atividade propõe que o aluno construa uma aplicação com múltiplas telas, implemente a navegação entre elas e utilize a passagem de parâmetros como forma de compartilhar dados. Também é avaliada a organização do projeto, o uso correto das ferramentas propostas e a evolução do desenvolvimento por meio dos commits no repositório.


## Commit "Passagem obrigatória de parametro na PerfilScreen"

Neste commit foi implementada a passagem de parâmetro para a tela de perfil. Inicialmente, foi adicionado o parâmetro nome do tipo String no construtor da função PerfilScreen, permitindo que esse valor seja exibido dinamicamente ao lado do título “PERFIL” na interface.

Em seguida, foi realizada a alteração na navegação da MenuScreen, onde a rota do botão de perfil passou a enviar o valor "Joao" através do caminho "perfil/Joao", demonstrando na prática o envio de dados entre telas.

Por fim, a MainActivity foi ajustada para suportar esse parâmetro na rota, incluindo a variável nome na definição do NavHost. Também foi definido um valor padrão ("Usuário Genérico") para garantir que a aplicação continue funcionando corretamente mesmo quando nenhum valor for informado na navegação.

## Commit "Passagem opcional de parametros na PedidosScreen"

Neste commit foi implementada a passagem de parâmetro para a tela de pedidos. Inicialmente, foi adicionado o parâmetro cliente do tipo String? no construtor da função PedidosScreen, permitindo que esse valor seja exibido dinamicamente no título da tela, junto ao texto “PEDIDOS”.

Além disso, foi realizada uma correção na exibição do texto, unificando a chamada para que o nome do cliente seja apresentado corretamente como “PEDIDOS - [cliente]”.

Em seguida, a rota na MainActivity foi ajustada para suportar o envio desse parâmetro utilizando query parameter ("pedidos?cliente={cliente}"). Também foi definido um valor padrão ("Cliente generico") por meio do navArgument, garantindo que a aplicação funcione mesmo quando nenhum valor for informado na navegação.

Por fim, ao navegar para a tela de pedidos, o valor do parâmetro é recuperado através de it.arguments?.getString("cliente") e passado para a PedidosScreen, completando o fluxo de envio e exibição de dados entre telas.

## Commit "inserindo valor ao parametro opcional de na PedidosScreen"

Neste commit foi realizada a implementação do envio de parâmetro na navegação para a tela de pedidos. Especificamente, foi alterada a ação do botão na MenuScreen, que anteriormente navegava apenas para a rota "pedidos", passando agora a enviar o valor "Cliente XPTO" como parâmetro por meio da rota "pedidos?cliente=Cliente XPTO".

Com essa modificação, ao acionar o botão, o nome do cliente é enviado para a PedidosScreen, permitindo que ele seja exibido dinamicamente na interface.

## Commit "Passagem de multiplos parametros na PerfilScreen"

Neste commit foi realizada a extensão da passagem de parâmetros para a tela de perfil, incluindo um novo dado: a idade do usuário. Para isso, o construtor da função PerfilScreen foi alterado para receber um parâmetro adicional idade do tipo Int, permitindo que essa informação seja exibida dinamicamente na interface junto ao nome do usuário.

Também foi feita a atualização do elemento de texto da tela, passando a apresentar tanto o nome quanto a idade (por exemplo: “PERFIL - João, 20 anos”), enriquecendo a exibição das informações.

Na MenuScreen, o botão de navegação para a tela de perfil foi ajustado para enviar, além do nome, o valor correspondente à idade como parâmetro na rota.

Além disso, na MainActivity, a rota foi atualizada para o formato "perfil/{nome}/{idade}", permitindo o recebimento de múltiplos parâmetros. Foram definidos explicitamente os arguments da rota utilizando navArgument, onde o parâmetro nome foi configurado como String (NavType.StringType) e o parâmetro idade como Int (NavType.IntType). Por fim, também foi considerado o uso de valores padrão para evitar falhas na aplicação caso algum parâmetro não seja informado.