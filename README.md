<h1>Portfólio das APIs - Emanuele Campos</h1>
<p align="justify">Trabalho de Graduação na modalidade Portfólio das Aprendizagens a partir de Projeto Integrador (APIs),
apresentado à Faculdade de Tecnologia de São José dos Campos,
como parte dos requisitos necessários para a obtenção do título de Tecnólogo em Banco de Dados.</p>
<hr>

<h2>Sobre mim</h2>
<p align="center"><img src="https://user-images.githubusercontent.com/88864112/282265843-d14d801d-c95c-443b-b0ac-4651f9d2d5e2.png" width="20%"></p>
<p align="justify"> Atualmente atuando como Analista de QA. Minha jornada na Tecnologia da Informação começou em 2019 na Unifesp, onde inicialmente me dediquei a estudos interdisciplinares em Ciências e Tecnologia. No entanto, optei por migrar para a Fatec, focando especificamente no curso de Banco de Dados. Minha experiência como Analista de QA na Touch Tec desde maio de 2022 tem sido enriquecedora. Durante esse período, aprimorei minhas habilidades em ferramentas como Postman, Confluence, Jira, Cypress, Git e jUnit, além de consolidar minha compreensão das metodologias ágeis, com destaque para o Scrum.</p>
<p align="justify"> Possuo habilidades técnicas abrangentes, desde a manipulação de bancos de dados como SQL Server, Postgre e Oracle, até a programação em linguagens como Python, C, Java, SpringBoot, Quarkus, Vue, JavaScript, Node.js, HTML e CSS. Reforcei essas habilidades através de cursos na Udemy, abordando temas essenciais como Python, Java, Desenvolvimento Front-end e Testes Automatizados.</p>
<p align="justify">Caso tenha interesse em saber mais sobre minha trajetória profissional e projetos, convido-o a visitar meu perfil no LinkedIn e meu repositório no GitHub.</p>
<p align="center">• <a href="https://www.linkedin.com/in/ecampos14/">LinkedIn</a> • <a href="https://github.com/ecampos14">GitHub</a> •</p>
<hr>

# Projeto 1 - 2º semestre de 2021
Empresa parceira: Projeto Interno

<p align="center">
  <img src="https://user-images.githubusercontent.com/88864112/143785694-09c566e8-8911-4b14-8231-77199dcd8079.jpg" height="300"/>

A Faculdade de Tecnologia de São José dos Campos foi criada no dia 2 de março de 2006, é uma Faculdade Pública Estadual e todos os cursos oferecidos são gratuitos.

## Visão do Projeto
Foi desenvolvido um projeto desktop, usando a linguagem de programação Python, para coletar, tratar e visualizar dados da COVID-19 no estado de São Paulo. O protótipo buscava fornecer informações detalhadas sobre a situação da pandemia por meio de várias visualizações de dados contextuais. A principal ênfase foi na manipulação offline de dados no formato CSV, minimizando a dependência de APIs prontas e relatórios de sites governamentais.

<p align="center">
  <img src="https://raw.githubusercontent.com/ecampos14/TG-Portfolio-API/main/1°SEM/Obtos%20por%20municipio.PNG" width="100%" height="100%">

## Tecnologias Utilizadas

<details>
<summary>Back-End</summary>

* [Python](https://www.python.org)

</details>

<details>
<summary>Reuniões e Comunicação</summary>

* [Discord](https://discord.com/?msclkid=b4f5af84b8f811ecbd81c127a0ae68a7)

* [Whatsapp](https://www.whatsapp.com/)

</details>

<details>
<summary>Outras Ferramentas</summary>

* [Github](https://github.com/)

* [Pycharm IDE](https://www.jetbrains.com/pt-br/pycharm/)

</details>

## Contribuições pessoais
Nesse Projeto atuei como Master e no desenvolvimento de features e estruturas do backend da ferramenta. O sistema foi construído em Python. No desenvolvimento deste projeto, diversos desafios foram enfrentados e realizados pelo time.

<details>
<summary>Atualização do csv</summary>
No Python, foi feita a função que mantinha a fonte de dados do csv atualizada.
<hr>
<pre><code> 
th = os.path.expanduser('~\Documents\caso_full.csv.gz')
output = os.path.expanduser('~\Documents\caso_full.csv')

def atualizar():
    print("Iniciando o download do arquivo.")
    url = 'https://data.brasil.io/dataset/covid19/caso_full.csv.gz'  # link para o arquivo fornecido pelo site Brasil.IO
    r = requests.get(url, allow_redirects=True)

    with open(path, 'wb') as f:
        f.write(r.content)
        print("Download do arquivo concluído.")
        """Após o download do arquivo, salva na pasta documentos"""

    with gzip.open(path, 'rb') as f_in:
        with open(output, 'wb') as f_out:
            shutil.copyfileobj(f_in, f_out)
        """Extrai o arquivo da fila .GZ na pasta Documentos do usuário"""
        print("Extração concluída.")
</code></pre>
<body>
  <h5>Esta função baixa um arquivo comprimido relacionado à COVID-19, o salva localmente, e em seguida, realiza a extração desse arquivo comprimido. O código parece depender de bibliotecas externas como requests, gzip e shutil</h5>
</body>
</details>

<details>
<summary>Tratamento de dados com pandas </summary>
Foi trabalhando com dados temporais, criando novas variáveis e realizando operações de filtragem e agregação no DataFrame pandas.
<pre><code>   
df = df.drop_duplicates()  # retira valores duplicados.
df['data'] = pd.to_datetime(df['data'])  # cria uma coluna de data
df['ano'] = pd.DatetimeIndex(df['data']).year  # cria uma coluna de ano
df['mes'] = pd.DatetimeIndex(df['data']).month  # cria uma coluna de mes
df['mes_nome'] = df['data'].dt.strftime('%B')  # transforma o numero da coluna 'mes' para nome do mes
df['mes_ano'] = df['mes_nome'].astype(str) + "-" + df['ano'].astype(str)  # concatena mes e ano
df['dia'] = pd.DatetimeIndex(df['data']).day
df['chave'] = df['cidade'] + df['mes_nome'] + df['ano'].astype(str
	
'''Variáveis'''

dia_1 = date.today() - timedelta(days=1)
dia_1.strftime("%Y-%m-%d")

total_mortes_sp = df['mortes'].loc[df['estado'] == 'SP'].loc[
    df['data'] == str(dia_1)].sum()  
<body>
  <h5> O código manipula um DataFrame, adicionando colunas relacionadas a datas e cidades. Em seguida, calcula o total de mortes em São Paulo na data de ontem. Essas operações são úteis para análises temporais e agregações específicas em conjuntos de dados</h5>
</body>
</details>

Atuei em praticamente todas essas frentes, criando diferentes rotas e serviços para implementar funcionalidades no sistema. Minhas principais contribuições foram nas consultas de dados, tratamento e atualização de arquivos. No entanto, destaco meu papel principal nas tarefas de gestão, na parte organizacional do projeto.

## Aprendizados Efetivos HS
- Desenvolvimento de serviços update: Sei fazer com autonomia; <br/>
- Tratamento de dados, utilizando pandas: Sei fazer com autonomia; <br/>
- Criação da documentação e organização do projeto: Sei fazer com autonomia; <br/>

# Projeto 2 - 1º semestre de 2022

Empresa parceira: DOMROCK

![DOMROCK](https://github.com/ecampos14/Dom_Rock/blob/main/GIT/cabecario2.jpg)

A DOMROCK é uma empresa brasileira sediada em São José dos Campos - SP, localizada no Parque Tecnológico. Ela atua no tratamento e atualizações de dados em grande escala.

## Visão do Projeto

Uma aplicação desktop foi desenvolvida como solução para a gestão de ativação do cliente na plataforma Dom Rock. A empresa buscava uma solução orientada à entrada de dados de parâmetros e variáveis específicas de cada cliente, a fim de alocar recursos na plataforma Dom Rock. Essa aplicação também permitia a entrada de dados e a estimativa de consumo de recursos, baseada em critérios como o volume de dados do cliente, quantidade de usuários, entre outros. Além disso, a aplicação tinha a capacidade de gerar relatórios e consultas. Um aspecto crucial do desenvolvimento foi a modelagem apropriada da base de dados, visando futuras integrações com outros sistemas.

![Protótipo](https://github.com/ecampos14/Dom_Rock/blob/main/GIT/prototipo.gif)

## Tecnologias Utilizadas
<details>
<summary>Front-End</summary>

* [JavaFX Scene Builder 3](https://www.oracle.com/java/technologies/javafxscenebuilder-1x-archive-downloads.html)
</details>

<details>
<summary>Back-End</summary>

* [Java](https://www.java.com/pt-BR/?msclkid=7faa842eb8f811ecab39772d4c1ae90b)

</details>

<details>
<summary>Banco de Dados</summary>

* [SQL Server Nuvem Azure](https://azure.microsoft.com/pt-br/services/sql-database/campaign/)
</details>

<details>
<summary>Reuniões e Comunicação</summary>

* [Discord](https://discord.com/?msclkid=b4f5af84b8f811ecbd81c127a0ae68a7)

* [Whatsapp](https://www.whatsapp.com/)

* [Slack](https://slack.com/intl/pt-br/?msclkid=c00e628eb8f811ecaef374bb86d7f056)
</details>

<details>
<summary>Outras Ferramentas</summary>

* [Github](https://github.com/)

* [Eclipse IDE](https://www.eclipse.org/downloads/)

* [IntelliJ IDE](https://www.jetbrains.com/idea/promo/?msclkid=6ae44e88c2811d86c0ae2cdbd94ffcfb&utm_source=bing&utm_medium=cpc&utm_campaign=AMER_en_BR_IDEA_Branded&utm_term=intellij&utm_content=intellij%20idea)

* [Jira](https://www.atlassian.com/br/software/jira?msclkid=c8e971f7b8f811ec957d13ca3bfc6c1b)

* [Figma](https://www.figma.com/)

</details>

Neste projeto, houve a utilização dos serviços do Java no back-end. Foi utilizado em sua construção, no front-end, o JavaFX utilizando o Scene Builder. A conexão com o banco de dados e a manutenção do banco para alterações foram realizadas por meio de migrations. A base de dados utilizada foi mantida, utilizando o SQL Server.

## Contribuições pessoais
Desenvolvimento de features e estruturas do backend da ferramenta. O sistema foi construído em Java. No desenvolvimento deste projeto, diversos desafios foram enfrentados e realizados pelo time do backend.

<details>
<summary>Registro e consultas dos dados</summary>
No Java, foi feito o registro dos clientes, podendo associá-los a cada nível do produto, dividido em escopo, bronze, silver e gold.
<hr>
<pre><code> 
public class EscopoDAO {
    Connection con;
    PreparedStatement stm;
    ResultSet rs;

    public EscopoDTO consultaId(String cnpj) {
        try (Connection con = new ConnectionFactory().conectaBD()) {
            EscopoDTO objescopoDTO = new EscopoDTO();
            stm = con.prepareStatement("Select * from Cliente where cnpj = ?");
            stm.setString(1, cnpj);
            rs = stm.executeQuery();

            if (rs.next()) {
                objescopoDTO.setCnpj(rs.getString("cnpj"));
                objescopoDTO.setRazaoSocial(rs.getString("razao_social"));
                objescopoDTO.setIdCliente(rs.getString("id_cliente"));
                return objescopoDTO;
            } else {
                return null;
            }

        } catch (SQLException ex) {
            return null;
        }
    }
</code></pre>
<body>
    <h5>O trecho Java pertence à classe EscopoDAO e inclui o método consultaId. Este método realiza consultas no banco de dados para obter informações de clientes com base no CNPJ fornecido. Utiliza boas práticas, como parametrização para prevenir injeção de SQL, e emprega o "try-with-resources" para garantir o fechamento adequado de recursos, como conexões.</h5>
</body>
</details>

<details>
<summary>Atualização de registros de clientes</summary>
Para atualizar registros complexos, como clientes, foi criado método no controller que possibilita a atualização dos dados de um cliente já existente no banco de dados.
<pre><code>
@FXML
void btn_att_salvar() {
    if(txt_att_razao_social.getText().equals("") || txt_att_cnpj.getLength() != 14) {
        exibiDialogoERRO("ERRO! Por favor, insira todos os campos corretamente.");
    } else {
        clienteSelecionado = table_cliente.getSelectionModel().getSelectedItem();

        clienteSelecionado.setCnpj(txt_att_cnpj.getText());
        clienteSelecionado.setRazao_social(txt_att_razao_social.getText());
        String segmento = box_att_segmento.getSelectionModel().getSelectedItem().toString();
        clienteSelecionado.setSegmento(segmento);
        try {
            dao.atualizar(clienteSelecionado);
            exibiDialogoINFO("Cliente ATUALIZADO com sucesso!");
            abas.getSelectionModel().select(consultar);
            btn_consulta_cnpj();
            atualizar.setDisable(true);
        } catch (Exception e) {
            exibiDialogoERRO("ERRO! Falha ao ATUALIZAR.");

        }
    }
}
</code></pre>
<body>
    <h5>O método btn_att_salvar trata da lógica de atualização de informações de um cliente em uma aplicação JavaFX. Ele verifica se os campos obrigatórios (razão social e CNPJ de 14 caracteres) foram preenchidos corretamente. Se não, exibe um diálogo de erro. Caso contrário, atualiza o cliente selecionado na tabela com os novos dados, realiza a atualização no banco de dados via o método atualizar da classe dao, e, em caso de sucesso, exibe um diálogo informativo.<h5>
</body>
</details>

<details>
<summary>Disponibilização de tabelas</summary>
Foi utilizado o JavaFX para a criação visual da tabela, usando o Java para a população dos dados na tabela bronze.
<pre><code>   
List<BronzeDTO> ativacaoDTOs = new ArrayList<BronzeDTO>();
produtoAtivacaoObservableList = FXCollections.observableList(ativacaoDTOs);

colfontedadoBronze.setCellValueFactory(new PropertyValueFactory<SilverDTO, String>("idFonteDado"));
colProduto.setCellValueFactory(new PropertyValueFactory<BronzeDTO, String>("nomeProduto"));
colFormato.setCellValueFactory(new PropertyValueFactory<BronzeDTO, String>("formato"));
colSistema.setCellValueFactory(new PropertyValueFactory<BronzeDTO, String>("sistema"));
colFrequencia.setCellValueFactory(new PropertyValueFactory<BronzeDTO, String>("frequencia"));
colOrigem.setCellValueFactory(new PropertyValueFactory<BronzeDTO, String>("origenDado"));
colVolume.setCellValueFactory(new PropertyValueFactory<BronzeDTO, String>("volume"));

tabelaBronze.setItems(produtoAtivacaoObservableList);
</code></pre>
<body>
    <h5>O código apresenta a inicialização e configuração de uma tabela JavaFX associada a objetos do tipo BronzeDTO. Primeiro, uma lista observável (produtoAtivacaoObservableList) é criada a partir de uma lista vazia de objetos BronzeDTO. Em seguida, as colunas da tabela são vinculadas aos atributos correspondentes da classe BronzeDTO usando PropertyValueFactory. Cada coluna representa um atributo específico.</h5>
</body>
</details>

Atuei em praticamente todas estas frentes, criando diferentes rotas e serviços para a implementação de várias features do sistema. Minhas principais contribuições foram nas consultas dos dados, criação do CRUD da tela de bronze e silver, disponibilização de dados em diferentes formatos de tabelas na nossa ferramenta.

## Aprendizados Efetivos HS
- Desenvolvimento de serviços CRUD: Sei fazer com autonomia.
- Desenvolvimento de aplicações desktop usando Java: Sei fazer com autonomia.
- Desenvolvimento de tabelas em JavaFX: Sei fazer com autonomia.
- Utilização de ORM's com banco relacional: Sei fazer com autonomia.

# Projeto 3 - 2º semestre de 2022
Empresa parceira: IACIT
<p align="center"><img src="https://github.com/fluffyfatec/Iacit/blob/Sprint-1/GIT/cabecario%20(3).jpg" height="300"/>

Um importante polo da indústria aeroespacial brasileira, fundada em 1986, a IACIT é uma empresa brasileira com sede em São José dos Campos - SP. Com capacitação no desenvolvimento de produtos e sistemas aplicados  para o segmento de navegação aérea, com certificação como Empresa Estratégica de Defesa (EED).

## Visão do Projeto
Foi desenvolvido um software web para a empresa Iacit que possibilita a automatização desde o download, o processamento dos dados e a persistência dos dados no banco de dados de forma simplificada dos dados meteorológicos. Além disso, também será possível realizar a filtragem desses dados por temperatura, umidade, estações, vento, pressão atmosférica, radiação global e precipitação, além da diversa visualizações desses dados. Contudo, fpi desenvolvido tambem níveis de usuários juntamente com o painel administrativo possibilitando a exportação dos relatórios a partir dos dados.
<p align="center">
      <img src="https://github.com/fluffyfatec/Iacit/blob/Sprint-2/GIT/VID-20221009-WA0013%20(2).gif" width="100%" height="100%">
<p align="center">    
	
## Tecnologias Utilizadas
<details>
<summary>Front-End</summary>

* [JavaScript](https://www.javascript.com)
* [HTML](https://www.w3schools.com/css/)
* [CSS](https://www.w3schools.com/css/)
</details>

<details>
<summary>Back-End</summary>

* [Java](https://www.java.com/pt-BR/?msclkid=7faa842eb8f811ecab39772d4c1ae90b)
 
* [Python](https://www.python.org/downloads/)

* [Spring boot](https://spring.io/projects/spring-boot)

</details>

<details>
<summary>Banco de Dados</summary>

* [PostgreSQL](https://www.postgresql.org/download/)
</details>
<details>
<summary>Reuniões e Comunicação</summary>

* [Discord](https://discord.com/?msclkid=b4f5af84b8f811ecbd81c127a0ae68a7)

* [Whatsapp](https://www.whatsapp.com/)

* [Slack](https://slack.com/intl/pt-br/?msclkid=c00e628eb8f811ecaef374bb86d7f056)
</details>

<details>
<summary>Outras Ferramentas</summary>

* [Github](https://github.com/)

* [Eclipse IDE](https://www.eclipse.org/downloads/)

* [IntelliJ IDE](https://www.jetbrains.com/idea/promo/?msclkid=6ae44e88c2811d86c0ae2cdbd94ffcfb&utm_source=bing&utm_medium=cpc&utm_campaign=AMER_en_BR_IDEA_Branded&utm_term=intellij&utm_content=intellij%20idea)

* [Azure DevOps](https://dev.azure.com/iacitAPI/iacitAPI/)

* [Photoshop](https://www.adobe.com/br/products/photoshop.html?sdid=KQPOM&mv=search&ef_id=d67181c6b224183a4875e395ae54f4bf:G:s&s_kwcid=AL!3085!10!79302406606568!79302288716688&msclkid=d67181c6b224183a4875e395ae54f4bf)
</details>

Neste projeto houve a utilização dos serviços do Spring como API do back-end.  foi utilizado em sua construção, no front-end a linguagem Javascript, juntamente com o Ajax.
Assim foram programadas todas as rotas HTTP, conexão com o banco de dados e manutenção do banco para alterações, por meio de migrations.
A base de dados utilizada foi mantida, utilizando o PostgreSQL.

## Contribuições pessoais
Desenvolvimento de features e estruturas do backend da ferramenta. O sistema foi construído em Java, com Spring. No desenvolvimento deste projeto, diversos desafios foram enfrentados e realizados pelo time do backend. 
<details>
<summary>Registro e consultas dos dados</summary>
  No Java com Spring, uso o Spring Data JPA para registrar e consultar dados. Ele oferece interfaces de repositório que estendem JpaRepository, proporcionando métodos prontos para operações de dados. <hr>
<pre><code> @Repository
public interface EstacaoRepository extends JpaRepository<EstacaoModal, String> {
	@Query("SELECT u FROM estacao u WHERE u.codWmo = :codWmo")
	public List<EstacaoModal> listar(@Param("codWmo") String codWmo);
  
	@Query(value = "SELECT * FROM estacao", nativeQuery = true)
	
	List<EstacaoModal> listarAllEstacoes();
	EstacaoModal findByEstacaoNome(String estacaoNome); 
 }
</code></pre>
<body>
  <h5>A interface "EstacaoRepository" é uma extensão da classe "JpaRepository" que fornece métodos para operações básicas de persistência de dados. Eu implementei consultas personalizadas usando a anotação "@Query" do Spring Data JPA para selecionar instâncias da entidade "estacao" com base em critérios específicos, como o valor do atributo "codWmo" e o nome da estação. Também adicionei um método para listar todas as estações na tabela "estacao" usando uma consulta SQL nativa. No geral, essa interface me ajudou a facilitar o acesso e a manipulação de dados relacionados às estações.</h5>
</body>
</details>
  
<details>
<summary>Atualização de registros complexos como o Usuario</summary>
  Para atualizar registros complexos, como um usuario, mapeio-os como entidades JPA e uso o Spring Data JPA para atualizá-los. Recupero a entidade, faço as modificações necessárias e salvo as alterações com o método save().
<pre><code>
  public ModelAndView execute(UsuarioRequestDTO data) {
    ModelAndView modelAndView = new ModelAndView();
    UsuarioModal userAdmin = usuarioRepository.findByUsuarioUsername(data.getUsuario_nome_adm());   
    PermissaoModal permissao = permissaoRepository.findByPermissaoNome(data.getNome_permissao());
    UsuarioModal user = usuarioRepository.findByUsuarioUsername(data.getUsuario_username());
    BCryptPasswordEncoder encode = new BCryptPasswordEncoder();

    String senhaEncriptografada = encode.encode(data.getUsuario_senha());

    user.setCodPermissao(permissao);
    user.setUsuarioCadastrante(userAdmin);
    user.setUsuarioNome(data.getUsuario_nome());
    user.setUsuarioSenha(senhaEncriptografada);
    user.setUsuarioUsername(data.getUsuario_username());
    user.setUsuarioAlterou(userAdmin);

    user = usuarioRepository.save(user); 

    modelAndView.addObject("user", user);
    modelAndView.setViewName("HfefCadUsuario");
    return modelAndView;
}
</code></pre>
<body>
  <h5>Neste código, trato de uma operação de atualização de usuário no sistema. Recebo um objeto `UsuarioRequestDTO` contendo os dados atualizados do usuário e utilizo os repositórios para buscar os objetos relacionados. Em seguida, criptografo a senha fornecida pelo usuário. Atualizo as propriedades do usuário com os dados do DTO e salvo o objeto `user` novamente no repositório. Por fim, configuro um objeto `ModelAndView` com o usuário atualizado e o retorno para a view "HfefCadUsuario", indicando que a atualização foi realizada com sucesso.</h5>
</body> 
</details>  
   
<details>
<summary>Disponibilização de documentos em diferentes formatos de grafico na nossa ferramenta</summary>
  Utilizo bibliotecas Java, como Chart.js, para gerar gráficos em diversos formatos. Integrando esses gráficos à ferramenta, os disponibilizo aos usuários.
<pre><code>   
const ctx1 = document.getElementById('graficoUmidade1').getContext('2d');
const myChart1 = new Chart(ctx1, {
type: 'line',            
data: {
    labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'],
    datasets: [{
        label: '# of Votes',
        data: [12, 19, 3, 5, 2, 3],
        backgroundColor: [
            'rgba(255, 99, 132, 0.2)',
            'rgba(54, 162, 235, 0.2)',
            'rgba(255, 206, 86, 0.2)',
            'rgba(75, 192, 192, 0.2)',
            'rgba(153, 102, 255, 0.2)',
            'rgba(255, 159, 64, 0.2)'
        ],
        </code></pre>
<body>
  <h5>Neste código, eu utilizei a biblioteca Chart.js para criar um gráfico de linha em um elemento do meu documento HTML. O objetivo era exibir dados de um conjunto de votos, onde cada voto é representado por rótulos e valores. Cada rótulo representa uma categoria e cada valor representa a quantidade de votos correspondente a essa categoria. Para tornar a visualização mais intuitiva, defini a cor de fundo das barras do gráfico utilizando a propriedade `backgroundColor`. Essa configuração me permitiu visualizar os dados de forma mais clara, identificando facilmente as diferentes categorias através das cores. No exemplo que eu forneci, pude exibir seis categorias distintas juntamente com as suas respectivas quantidades de votos.</h5>
</body>
</details>
 
<details>
<summary>Disponibilização de relatorio em todas as telas da aplicação</summary>
  Com Thymeleaf, JSP ou bibliotecas de geração de relatórios, como JasperReports ou Apache POI, crio relatórios em PDF, Excel, CSV, entre outros. Esses relatórios são acessíveis por links ou botões nas telas da aplicação.
<pre><code>
    public static ByteArrayInputStream exportarPdfPrecipitacao (List<ViewPrecipitacaoModal> viewPrecipitacaoModals) throws IOException {

        //Criando o documento PDF
        Document document = new Document(PageSize.A4.rotate(), 25, 25, 25, 25);
        ByteArrayOutputStream out = new ByteArrayOutputStream();

        try {

            //Criando a tabela para o relatório
            PdfPTable table = new PdfPTable(2);
            table.setWidthPercentage(100);
            table.setWidths(new int[] { 4, 4});

            //Criando o cabeçalho da tabela
            Font headFont = FontFactory.getFont(FontFactory.HELVETICA_BOLD, 14, BaseColor.WHITE);

            PdfPCell hcell;
</code></pre>
<body>
  <h5>Neste código, foi criado um documento PDF usando a biblioteca iText para Java. O documento é configurado com o tamanho da página A4 no formato paisagem (rotacionado) e são definidas as margens. Em seguida, foi criada uma tabela para o relatório usando a classe `PdfPTable`, com duas colunas. O cabeçalho da tabela é definido com a fonte `HELVETICA_BOLD` e tamanho 14. Um objeto `PdfPCell` é criado para armazenar cada célula da tabela.</h5>
</body>
</details>
   
<details>
<summary>Criação e recuperação de logs e atualização dos registros de usuários e atas</summary>
  Uso bibliotecas de logging, como Log4j ou SLF4J, para criar logs com informações relevantes. Com o Spring Data JPA, recupero registros, faço atualizações e salvo as       alterações nos dados do usuário e atas.
<pre><code>
@Service
public class LogService {

	    @Autowired 
	    LogRepository logrep;

	    public ModelAndView listar(LogUsuarioDTO logusuario) {
	    	ModelAndView  moden= new ModelAndView();
	    	LogUsuarioModal logAtiva = logrep.findByLogCodUsuario(logusuario.getLogCodUsuario());
	 
	        moden.addObject("estacaoAtiva", logAtiva);
	 		moden.setViewName("UsuarioUpEst");
	 		
	 		return moden;
	    }
</code></pre>

<body>
  <h5>Nesta classe, o `LogService`, eu criei um serviço no Spring responsável por lidar com operações relacionadas a logs de usuários. No método `listar`, eu utilizei a anotação `@Autowired` para injetar o repositório `LogRepository` e buscar informações do log do usuário. Em seguida, criei um objeto `ModelAndView` para retornar os dados do log de usuário para a view "UsuarioUpEst". Para isso, obtive o objeto `logAtiva` do repositório com base no código do usuário fornecido no DTO `logusuario`. Adicionei esse objeto ao `ModelAndView` e o retornei para a view.
</h5>
</body>
</details>
      
Atuei em praticamente todas estas frentes, criando diferentes rotas e serviços para a implementação de várias features do sistema. Minhas principais contruibuições foram nas consultas dos dados e disponibilização de documentos em diferentes formatos de grafico na nossa ferramenta.

## Aprendizados Efetivos HS
- Desenvolvimento de serviços CRUD: Sei fazer com autonomia; <br/>
- Desenvolvimento de ApiRest utilizando SpringBoot: Sei fazer com autonomia; <br/>
- Desenvolvimento de graficos para aplicação usando Chart.js: Sei fazer com autonomia; <br/>
- Utilização de ORM's com banco relacional: Sei fazer com autonomia; <br/>

# Projeto 4 - 1º semestre de 2023
Empresa parceira: Embraer

<p align="center"><img src="https://github.com/octopusBD/apiEmbraer4-sem/blob/b92089563bafd98ceac265983ccba1574dacab6e/Imagens%20documentacao/doc/inicial.png" height="300"/>

Embraer, é uma empresa brasileira, fabricante de aviões comerciais, executivos, agrícolas e militares, peças aeroespaciais, serviços e suporte na área. A empresa tem sede no município de São José dos Campos, interior do estado de São Paulo, e possui diversas unidades no Brasil e no exterior, inclusive joint ventures na China e em Portugal.

## Visão do Projeto
Foi desenvolvido um software web para a empresa Embraer que possibilita encontrar as aeronaves, associadas aos pilotos, pois atualmente, muitos pilotos trabalham como freelancers e não operam apenas uma aeronave/frota, o que dificulta o reconhecimento fácil e simples de determinados equipamentos e versões de software instalados na aeronave. Além disso, os pilotos nem sempre têm acesso rápido a todos os manuais e documentos da aeronave, o que prejudica o seu conhecimento sobre ela e suas capacidades.

  <p align="center">
      <img src=https://raw.githubusercontent.com/octopusBD/apiEmbraer4-sem/Sprint-4/Imagens%20documentacao/doc/gifSprint4.gif width="100%" height="100%">
<p align="center">      

## Tecnologias Utilizadas
<details>
<summary>Front-End</summary>

* [vue](https://vuejs.org/)
* [HTML](https://www.w3schools.com/css/)
* [CSS](https://www.w3schools.com/css/)

</details>

<details>
<summary>Back-End</summary>

* [Java](https://www.java.com/pt-BR/?msclkid=7faa842eb8f811ecab39772d4c1ae90b)

* [Spring boot](https://spring.io/projects/spring-boot)

</details>

<details>
<summary>Database</summary>

* [Oracle Autonomous Database](https://www.oracle.com/autonomous-database/)
</details>

<details>
<summary>Outras Ferramentas</summary>

* [Discord](https://discord.com/?msclkid=b4f5af84b8f811ecbd81c127a0ae68a7)

* [Whatsapp](https://www.whatsapp.com/)

* [Slack](https://slack.com/intl/pt-br/?msclkid=c00e628eb8f811ecaef374bb86d7f056)
</details>

Neste projeto houve a utilização dos serviços do Spring como API do back-end.  foi utilizado em sua construção, no front-end a linguagem Javascript, juntamente com o Vue.js.
Assim foram programadas todas as rotas HTTP, conexão com o banco de dados e manutenção do banco para alterações, por meio de migrations.
A base de dados utilizada foi mantida, utilizando o Oracle.

## Contribuições pessoais
Desenvolvimento de features e estruturas do backend da ferramenta. O sistema foi construído em Java, com Spring. No desenvolvimento deste projeto, diversos desafios foram enfrentados e realizados pelo time do backend. 
  
<details>
<summary>Registro e consultas dos dados</summary>
  No Java com Spring, uso o Spring Data JPA para registrar e consultar dados. Ele oferece interfaces de repositório que estendem JpaRepository, proporcionando métodos prontos para operações de dados. <hr>
 <pre><code> @Repository

    // LISTAR DISPONIBILIDADE POR ID //
	public List<ViewEstatisticaDisponibilidadeEntity> findByIdUsuario(Integer idUsuario) {
		return estatisticaDisponibilidadeRepository.findByIdUsuario(idUsuario);
	}

	// LISTAR PERMISSAO //
    public List<ViewEstatisticaUsuario> getAllPermissao() {
        return estatisticapermissao.findAll();
    }

</code></pre>
<body>
  <h5>Os métodos para operações básicas de persistência de dados. Eu implementei consultas personalizadas usando  Spring Data JPA para selecionar instâncias da entidade "ViewEstatisticaDisponibilidadeEntity" com base em critérios específicos, como o valor do atributo "IdUsuario". Também adicionei um método para listar todos os dados na tabela  usando uma consulta usando o JPA. No geral, o JPA me ajudou a facilitar o acesso e a manipulação de dados relacionados às visualizações.</h5>
</body>
</details>
  
<details>
<summary>Atualização de registros como o Usuario</summary>
  Para atualizar registros complexos, como um usuario, mapeio-os como entidades JPA e uso o Spring Data JPA para atualizá-los. Recupero a entidade, faço as modificações necessárias e salvo as alterações com o método save().
<pre><code>
   //@PreAuthorize("hasRole('ADMIN')")
		public UsuarioEntity atualizarUsuario(Integer idUsuario, UsuarioDTO usuarioNovo) {
		    Optional<UsuarioEntity> optionalUsuario = usuarioRepository.findById(idUsuario);
		    System.err.println(optionalUsuario);
		    System.err.println(usuarioNovo);
		    if (optionalUsuario.isPresent()) {
		        UsuarioEntity usuario = optionalUsuario.get();
		        usuario.setLoginUsuario(usuarioNovo.getLoginUsuario());
		        
		        //Optional<PermissaoEntity> optionalPermissao = permissaoRepository.findByIdPermissao(usuarioNovo.getIdPermissao().getIdPermissao());
		        Optional<PermissaoEntity> optionalPermissao = permissaoRepository.findByPermissao(usuarioNovo.getPermissao());
		        if (optionalPermissao.isPresent()) {
		            usuario.setIdPermissao(optionalPermissao.get());
		        }
	
		        return usuarioRepository.save(usuario);
		    } else {
}
</code></pre>
<body>
  <h5>Neste código, trato de uma operação de atualização de usuário no sistema. Recebo um objeto `UsuarioEntity` contendo os dados atualizados do usuário e utilizo os repositórios para buscar os objetos relacionados. Em seguida, criptografo a senha fornecida pelo usuário.</h5>
</body>
</details>  
   
<details>
<summary>Disponibilização de documentos em diferentes formatos de grafico na nossa ferramenta</summary>
  Utilizo bibliotecas Java, como Chart.js, para gerar gráficos em diversos formatos. Integrando esses gráficos à ferramenta, os disponibilizo aos usuários.
<pre><code>   
const dateTime = `${new Date().toLocaleDateString()} ${new Date().toLocaleTimeString()}`;
        const imgData = "https://cdn.discordapp.com/attachments/1075971608684023814/1111350679022346260/logo-dois.png";

        const titleWidth = doc.getStringUnitWidth(title) * doc.internal.getFontSize() / doc.internal.scaleFactor;
        const titleX = (doc.internal.pageSize.getWidth() - titleWidth) / 2;
        const titleHeight = 11; // Altura da primeira faixa
        const titleFontSize = 20; // Tamanho da fonte do título
        const titleY = 15 + (titleHeight - titleFontSize) / 2 + titleFontSize * 0.35;
        </code></pre>
<body>
  <h5>Neste código, eu utilizei a biblioteca Chart.js para criar um gráfico de linha em um elemento do meu documento HTML. Para tornar a visualização mais intuitiva, defini a cor de fundo das barras do gráfico utilizando a propriedade `backgroundColor`. Essa configuração me permitiu visualizar os dados de forma mais clara, identificando facilmente as diferentes categorias através das cores. No exemplo que eu forneci, pude exibir seis categorias distintas juntamente com as suas respectivas quantidades de votos.</h5>
</body>
</details>

<details>
<summary>Disponibilização de relatorio em todas as telas da aplicação</summary>
  Com Thymeleaf, JSP ou bibliotecas de geração de relatórios, como JasperReports ou Apache POI, crio relatórios em PDF. Esses relatórios são acessíveis por botões nas telas da aplicação.
<pre><code>
	public static ByteArrayInputStream exportarPdfConsulta (List<ViewListarLogicaEntity> viewsample) throws IOException {
		
			//Criando o documento PDF
		Document document = new Document(PageSize.A4.rotate(), 25, 25, 25, 25);
		ByteArrayOutputStream out = new ByteArrayOutputStream();

		try {
			//Criando a tabela para o relatório
			PdfPTable table = new PdfPTable(2);
			table.setWidthPercentage(100);
			table.setWidths(new int[] { 4, 4});
			
			
			//Criando o cabeçalho da tabela
			Font headFont = FontFactory.getFont(FontFactory.HELVETICA_BOLD, 14, BaseColor.WHITE);

			PdfPCell hcell;

			hcell = new PdfPCell(new Phrase("Item", headFont));
			hcell.setPaddingTop(9f);
			hcell.setFixedHeight(40f);
			hcell.setVerticalAlignment(Element.ALIGN_CENTER);
			hcell.setHorizontalAlignment(Element.ALIGN_CENTER);
			table.addCell(hcell);
 </code></pre>
<body>
<h5>Neste código, foi criado um documento PDF usando a biblioteca iText para Java. O documento é configurado com o tamanho da página A4 no formato paisagem (rotacionado) e são definidas as margens. Em seguida, foi criada uma tabela para o relatório usando a classe `PdfPTable`, com duas colunas. O cabeçalho da tabela é definido com a fonte `HELVETICA_BOLD` e tamanho 14. Um objeto `PdfPCell` é criado para armazenar cada célula da tabela.</h5>
</body>
</details>
      
   
Atuei em praticamente todas estas frentes, criando diferentes rotas e serviços para a implementação de várias features do sistema. Minhas principais contruibuições foram nas consultas dos dados e disponibilização de documentos em diferentes formatos de grafico na nossa ferramenta.

## Aprendizados Efetivos HS
- Desenvolvimento de serviços CRUD: Sei fazer com autonomia; <br/>
- Desenvolvimento de ApiRest utilizando SpringBoot: Sei fazer com autonomia; <br/>
- Desenvolvimento de graficos para aplicação usando Chart.js: Sei fazer com autonomia; <br/>
- Utilização de ORM's com banco relacional: Sei fazer com autonomia; <br/>
