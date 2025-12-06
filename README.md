Não obtive um resultado tão satisfatório!

Acredito que um dos principais problemas é que o meu dataset é pequeno demais (foi carregado pouco mais de 1700 imagens) para treinar uma WGAN-GP estável. Para este tipo de GAN e para o tipo de dataset que usei, acredito que eu precisaria de um dataset de 5 a 10 mil imagens, e com essas poucas amostras o modelo não aprendeu padrões reais, apenas gerou borrões.

Além disso, configurei o critic_iterations = 1, para que o código fosse mais otimizado e não levasse tantas horas rodando, o que praticamente foi como uma trava para a WGAN-GP funcionar. Acredito que deveria ter configurado de 3 a 5 iterações.

Outro ponto crítico é que minhas imagens parecem estar sendo carregadas com resolução diferente da esperada. é possivel ver que retorna 224×224 mesmo com transform de 64×64. Isso acaba atrapalhando o aprendizado, porque a arquitetura foi feita para 64×64. Isso indica erro no transform ou no carregamento do dataset.

Foi utilizado tambem o batch size de 32, que é baixo, e WGAN-GP é muito sensível a isso. Batches pequenos deixam o gradiente instável e pioram ainda mais o aprendizado com datasets pequenos.
