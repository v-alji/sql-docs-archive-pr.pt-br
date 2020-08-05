---
title: Incorporar uma tarefa Criação de Perfil de Dados no fluxo de trabalho do pacote | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling task [Integration Services], using output in workflow
ms.assetid: 39a51586-6977-4c45-b80b-0157a54ad510
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd3544586ac99f66b961f7961e4f4af4d9e4a4c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572633"
---
# <a name="incorporate-a-data-profiling-task-in-package-workflow"></a><span data-ttu-id="081c9-102">Incorporar uma tarefa Criação de Perfil de Dados no fluxo de trabalho do pacote</span><span class="sxs-lookup"><span data-stu-id="081c9-102">Incorporate a Data Profiling Task in Package Workflow</span></span>
  <span data-ttu-id="081c9-103">As tarefas de criação de perfil e limpeza de dados não são candidatas a um processo automatizado em seus estágios iniciais.</span><span class="sxs-lookup"><span data-stu-id="081c9-103">Data profiling and cleanup are not candidates for an automated process in their early stages.</span></span> <span data-ttu-id="081c9-104">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], a saída da tarefa Criação de Perfil de Dados normalmente exige uma análise visual e uma opinião humana para determinar se as violações relatadas são significativas ou demasiadas.</span><span class="sxs-lookup"><span data-stu-id="081c9-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], the output of the Data Profiling task usually requires visual analysis and human judgment to determine whether reported violations are meaningful or excessive.</span></span> <span data-ttu-id="081c9-105">Mesmo depois de reconhecer os problemas de qualidade dos dados, ainda é necessário fazer um planejamento cuidadoso para escolher a melhor abordagem de limpeza.</span><span class="sxs-lookup"><span data-stu-id="081c9-105">Even after recognizing data quality problems, there still has to be a carefully thought-out plan that addresses the best approach for cleanup.</span></span>  
  
 <span data-ttu-id="081c9-106">No entanto, depois de estabelecer os critérios de qualidade dos dados, você talvez queira automatizar a análise e limpeza periódicas da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="081c9-106">However, after criteria for data quality have been established, you might want to automate a periodic analysis and cleanup of the data source.</span></span> <span data-ttu-id="081c9-107">Considere estes cenários:</span><span class="sxs-lookup"><span data-stu-id="081c9-107">Consider these scenarios:</span></span>  
  
-   <span data-ttu-id="081c9-108">**Verificando a qualidade dos dados antes de uma carga incremental**.</span><span class="sxs-lookup"><span data-stu-id="081c9-108">**Checking data quality before an incremental load**.</span></span> <span data-ttu-id="081c9-109">Use a tarefa Criação de Perfil de Dados para calcular o Perfil de Razão Nula de Coluna dos novos dados previstos para a coluna CustomerName em uma tabela Clientes.</span><span class="sxs-lookup"><span data-stu-id="081c9-109">Use the Data Profiling task to compute the Column Null Ratio Profile of new data intended for the CustomerName column in a Customers table.</span></span> <span data-ttu-id="081c9-110">Se a porcentagem dos valores nulos for superior a 20%, envie uma mensagem de email com a saída de perfil para o operador e encerre o pacote.</span><span class="sxs-lookup"><span data-stu-id="081c9-110">If the percentage of null values is greater than 20%, send an e-mail message that contains the profile output to the operator and end the package.</span></span> <span data-ttu-id="081c9-111">Caso contrário, continue a carga incremental.</span><span class="sxs-lookup"><span data-stu-id="081c9-111">Otherwise, continue the incremental load.</span></span>  
  
-   <span data-ttu-id="081c9-112">**Automatizando a limpeza quando as condições especificadas são atendidas**.</span><span class="sxs-lookup"><span data-stu-id="081c9-112">**Automating cleanup when the specified conditions are met**.</span></span> <span data-ttu-id="081c9-113">Use a tarefa Criação de Perfil de Dados para calcular o Perfil de Inclusão de Valor da coluna Estado de uma tabela de pesquisa de estados e da coluna Código Postal/CEP de uma coluna de pesquisa de códigos postais.</span><span class="sxs-lookup"><span data-stu-id="081c9-113">Use the Data Profiling task to compute the Value Inclusion Profile of the State column against a lookup table of states, and of the ZIP Code/Postal Code column against a lookup table of zip codes.</span></span> <span data-ttu-id="081c9-114">Se a intensidade de inclusão dos valores de estado for inferior a 80%, mas a intensidade de inclusão dos valores de código postal/CEP for superior a 99%, esses resultados indicam duas coisas.</span><span class="sxs-lookup"><span data-stu-id="081c9-114">If the inclusion strength of the state values is less than 80%, but the inclusion strength of the ZIP Code/Postal Code values is greater than 99%, this indicates two things.</span></span> <span data-ttu-id="081c9-115">Primeiro, os dados de estado são incorretos.</span><span class="sxs-lookup"><span data-stu-id="081c9-115">First, the state data is bad.</span></span> <span data-ttu-id="081c9-116">Segundo, os dados de código postal/CEP são corretos.</span><span class="sxs-lookup"><span data-stu-id="081c9-116">Second, the ZIP Code/Postal Code data is good.</span></span> <span data-ttu-id="081c9-117">Inicie uma tarefa Fluxo de Dados que limpa os dados de estado executando uma pesquisa do valor de estado correto a partir do valor de código postal/CEP atual.</span><span class="sxs-lookup"><span data-stu-id="081c9-117">Launch a Data Flow task that cleans up the state data by performing a lookup of the correct state value from the current Zip Code/Postal Code value.</span></span>  
  
 <span data-ttu-id="081c9-118">Depois de estabelecer um fluxo de trabalho no qual é possível incorporar a tarefa Fluxo de Dados, você precisa entender as etapas necessárias para adicionar essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="081c9-118">After you have a workflow into which you can incorporate the Data Flow task, you have to understand the steps that are required to add this task.</span></span> <span data-ttu-id="081c9-119">A próxima seção descreve o processo geral de incorporação da tarefa Fluxo de Dados.</span><span class="sxs-lookup"><span data-stu-id="081c9-119">The next section describes the general process of incorporating the Data Flow task.</span></span> <span data-ttu-id="081c9-120">As duas seções finais descrevem como conectar a tarefa Fluxo de Dados diretamente a uma fonte de dados ou aos dados transformados do Fluxo de Dados.</span><span class="sxs-lookup"><span data-stu-id="081c9-120">The final two sections describe how to connect the Data Flow task either directly to a data source or to transformed data from the Data Flow.</span></span>  
  
## <a name="defining-a-general-workflow-for-the-data-flow-task"></a><span data-ttu-id="081c9-121">Definindo um fluxo de trabalho geral para a tarefa Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="081c9-121">Defining a General Workflow for the Data Flow Task</span></span>  
 <span data-ttu-id="081c9-122">O procedimento a seguir descreve a abordagem geral de uso da saída da tarefa Criação de Perfil de Dados no fluxo de trabalho de um pacote.</span><span class="sxs-lookup"><span data-stu-id="081c9-122">The following procedure outlines the general approach for using the output of the Data Profiling task in the workflow of a package.</span></span>  
  
#### <a name="to-use-the-output-of-the-data-profiling-task-programmatically-in-a-package"></a><span data-ttu-id="081c9-123">Para usar a saída da tarefa Criação de Perfil de Dados programaticamente em um pacote</span><span class="sxs-lookup"><span data-stu-id="081c9-123">To use the output of the Data Profiling task programmatically in a package</span></span>  
  
1.  <span data-ttu-id="081c9-124">Adicione e configure a tarefa Criação de Perfil de Dados em um pacote.</span><span class="sxs-lookup"><span data-stu-id="081c9-124">Add and configure the Data Profiling task in a package.</span></span>  
  
2.  <span data-ttu-id="081c9-125">Configure as variáveis de pacote para manter os valores que deseja recuperar dos resultados de perfil.</span><span class="sxs-lookup"><span data-stu-id="081c9-125">Configure package variables to hold the values that you want to retrieve from the profile results.</span></span>  
  
3.  <span data-ttu-id="081c9-126">Adicione e configure uma tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="081c9-126">Add and configure a Script task.</span></span> <span data-ttu-id="081c9-127">Conecte a tarefa Script à tarefa Criação de Perfil de Dados.</span><span class="sxs-lookup"><span data-stu-id="081c9-127">Connect the Script task to the Data Profiling task.</span></span> <span data-ttu-id="081c9-128">Na tarefa Script, grave o código que lê os valores desejados do arquivo de saída da tarefa Criação de Perfil de Dados e preencha as variáveis de pacote.</span><span class="sxs-lookup"><span data-stu-id="081c9-128">In the Script task, write code that reads the desired values from the output file of the Data Profiling task and populates the package variables.</span></span>  
  
4.  <span data-ttu-id="081c9-129">Nas restrições de precedência que conectam a tarefa Script às ramificações de downstream do fluxo de trabalho, grave expressões que usem os valores das variáveis para dirigir o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="081c9-129">In the precedence constraints that connect the Script task to downstream branches in the workflow, write expressions that use the values of the variables to direct the workflow.</span></span>  
  
 <span data-ttu-id="081c9-130">Ao incorporar a tarefa Criação de Perfil de Dados no fluxo de trabalho de um pacote, tenha esses dois recursos da tarefa em mente:</span><span class="sxs-lookup"><span data-stu-id="081c9-130">When incorporating the Data Profiling task into the workflow of a package, keep these two features of the task in mind:</span></span>  
  
-   <span data-ttu-id="081c9-131">**Saída da tarefa**.</span><span class="sxs-lookup"><span data-stu-id="081c9-131">**Task output**.</span></span> <span data-ttu-id="081c9-132">A tarefa Criação de Perfil de Dados grava sua saída em um arquivo ou uma variável de pacote em formato XML, de acordo com o esquema DataProfile.xsd.</span><span class="sxs-lookup"><span data-stu-id="081c9-132">The Data Profiling task writes its output to a file or a package variable in XML format according to the DataProfile.xsd schema.</span></span> <span data-ttu-id="081c9-133">Portanto, é necessário consultar a saída XML se você desejar usar os resultados de perfil no fluxo de trabalho condicional de um pacote.</span><span class="sxs-lookup"><span data-stu-id="081c9-133">Therefore, you have to query the XML output if you want to use the profile results in the conditional workflow of a package.</span></span> <span data-ttu-id="081c9-134">Você pode usar a linguagem de consulta Xpath facilmente para consultar essa saída XML.</span><span class="sxs-lookup"><span data-stu-id="081c9-134">You can easily use the Xpath query language to query this XML output.</span></span> <span data-ttu-id="081c9-135">Para estudar a estrutura dessa saída XML, você pode abrir um arquivo de saída de amostra ou o próprio esquema.</span><span class="sxs-lookup"><span data-stu-id="081c9-135">To study the structure of this XML output, you can open a sample output file or the schema itself.</span></span> <span data-ttu-id="081c9-136">Para abrir o arquivo de saída ou o esquema, use o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], outro editor de XML ou um editor de texto, como o Bloco de Notas.</span><span class="sxs-lookup"><span data-stu-id="081c9-136">To open the output file or schema, you can use [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], another XML editor, or a text editor, such as Notepad.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="081c9-137">Alguns resultados de perfil exibidos no Visualizador de Perfil de Dados são valores calculados que não são encontrados diretamente na saída.</span><span class="sxs-lookup"><span data-stu-id="081c9-137">Some of the profile results that are displayed in the Data Profile Viewer are calculated values that are not directly found in the output.</span></span> <span data-ttu-id="081c9-138">Por exemplo, a saída do Perfil de Razão Nula de Coluna contém o número total de linhas e o número de linhas que contêm valores nulos.</span><span class="sxs-lookup"><span data-stu-id="081c9-138">For example, the output of the Column Null Ratio Profile contains the total number of rows and the number of rows that contain null values.</span></span> <span data-ttu-id="081c9-139">É necessário consultar esses dois valores e, em seguida, calcular a porcentagem de linhas que contêm valores nulos para obter a razão nula de consulta.</span><span class="sxs-lookup"><span data-stu-id="081c9-139">You have to query these two values, and then calculate the percentage of rows that contain null values, to obtain the column null ratio.</span></span>  
  
-   <span data-ttu-id="081c9-140">**Entrada da tarefa**.</span><span class="sxs-lookup"><span data-stu-id="081c9-140">**Task input**.</span></span> <span data-ttu-id="081c9-141">A tarefa Criação de Perfil de Dados lê sua entrada a partir de tabelas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="081c9-141">The Data Profiling task reads its input from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables.</span></span> <span data-ttu-id="081c9-142">Portanto, é necessário salvar os dados que estejam na memória nas tabelas de preparação se você desejar criar perfis de dados que já tenham sido carregados e transformados no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="081c9-142">Therefore, you have to save data that is in memory to staging tables if you want to profile data that has already been loaded and transformed in the data flow.</span></span>  
  
 <span data-ttu-id="081c9-143">As seções a seguir aplicam esse fluxo de trabalho geral à criação de perfis de dados oriundos diretamente de uma fonte de dados externa ou transformados a partir da tarefa Fluxo de Dados.</span><span class="sxs-lookup"><span data-stu-id="081c9-143">The following sections apply this general workflow to profiling data that comes directly from an external data source or that comes transformed from the Data Flow task.</span></span> <span data-ttu-id="081c9-144">Essas seções também mostram como controlar os requisitos de entrada e saída da tarefa Fluxo de Dados.</span><span class="sxs-lookup"><span data-stu-id="081c9-144">These sections also show how to handle the input and output requirements of the Data Flow task.</span></span>  
  
## <a name="connecting-the-data-profiling-task-directly-to-an-external-data-source"></a><span data-ttu-id="081c9-145">Conectando a tarefa Criação de Perfil de Dados diretamente a uma fonte de dados externa</span><span class="sxs-lookup"><span data-stu-id="081c9-145">Connecting the Data Profiling Task Directly to an External Data Source</span></span>  
 <span data-ttu-id="081c9-146">A tarefa Criação de Perfil de Dados pode criar perfis de dados oriundos diretamente de uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="081c9-146">The Data Profiling task can profile data that comes directly from a data source.</span></span>  <span data-ttu-id="081c9-147">Para ilustrar esse recurso, o exemplo a seguir usa a tarefa Criação de Perfil de Dados para calcular um Perfil de Razão Nula de Coluna nas colunas da tabela Person.Address no banco de dados [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="081c9-147">To illustrate this capability, the following example uses the Data Profiling task to compute a Column Null Ratio Profile on the columns of the Person.Address table in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="081c9-148">Em seguida, esse exemplo usa uma tarefa Script para recuperar os resultados do arquivo de saída e popular as variáveis de pacote que podem ser usadas para direcionar o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="081c9-148">Then, this example uses a Script task to retrieve the results from the output file and populate package variables that can be used to direct workflow.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="081c9-149">A coluna AddressLine2 foi selecionada para este exemplo porque contém uma porcentagem alta de valores nulos.</span><span class="sxs-lookup"><span data-stu-id="081c9-149">The AddressLine2 column was selected for this simple example because this column contains a high percentage of null values.</span></span>  
  
 <span data-ttu-id="081c9-150">Este exemplo consiste nas seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="081c9-150">This example consists of the following steps:</span></span>  
  
-   <span data-ttu-id="081c9-151">Configuração de gerenciadores de conexões que se conectam à fonte de dados externa e ao arquivo de saída que vai conter os resultados do perfil.</span><span class="sxs-lookup"><span data-stu-id="081c9-151">Configuring the connection managers that connect to the external data source and to the output file that will contain the profile results.</span></span>  
  
-   <span data-ttu-id="081c9-152">Configuração das variáveis de pacote que vão manter os valores exigidos pela tarefa Criação de Perfil de Dados.</span><span class="sxs-lookup"><span data-stu-id="081c9-152">Configuring the package variables that will hold the values needed by the Data Profiling task.</span></span>  
  
-   <span data-ttu-id="081c9-153">Configuração da tarefa Criação de Perfil de Dados para calcular o Perfil de Razão Nula de Coluna.</span><span class="sxs-lookup"><span data-stu-id="081c9-153">Configuring the Data Profiling task to compute the Column Null Ratio Profile.</span></span>  
  
-   <span data-ttu-id="081c9-154">Configuração da tarefa Script para funcionar na saída XML da tarefa Criação de Perfil de Dados.</span><span class="sxs-lookup"><span data-stu-id="081c9-154">Configuring the Script task to work the XML output from the Data Profiling task.</span></span>  
  
-   <span data-ttu-id="081c9-155">Configuração das restrições de precedência que vão controlar quais ramificações de downstream do fluxo de trabalho são executadas com base nos resultados da tarefa Criação de Perfil de Dados.</span><span class="sxs-lookup"><span data-stu-id="081c9-155">Configuring the precedence constraints that will control which downstream branches in the workflow are run based on the results of the Data Profiling task.</span></span>  
  
### <a name="configure-the-connection-managers"></a><span data-ttu-id="081c9-156">Configurar os gerenciadores de conexões</span><span class="sxs-lookup"><span data-stu-id="081c9-156">Configure the Connection Managers</span></span>  
 <span data-ttu-id="081c9-157">Para este exemplo, há dois gerenciadores de conexões:</span><span class="sxs-lookup"><span data-stu-id="081c9-157">For this example, there are two connection managers:</span></span>  
  
-   <span data-ttu-id="081c9-158">Um gerenciador de conexões [!INCLUDE[vstecado](../../includes/vstecado-md.md)] que se conecta ao banco de dados [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="081c9-158">An [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that connects to the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span>  
  
-   <span data-ttu-id="081c9-159">Um gerenciador de conexões de arquivos que cria o arquivo de saída que armazenará os resultados da tarefa Criação de Perfil de Dados.</span><span class="sxs-lookup"><span data-stu-id="081c9-159">A File connection manager that creates the output file that will hold the results of the Data Profiling task.</span></span>  
  
##### <a name="to-configure-the-connection-managers"></a><span data-ttu-id="081c9-160">Para configurar os gerenciadores de conexões</span><span class="sxs-lookup"><span data-stu-id="081c9-160">To configure the connection managers</span></span>  
  
1.  <span data-ttu-id="081c9-161">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], crie um novo pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="081c9-161">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span>  
  
2.  <span data-ttu-id="081c9-162">Adicione um gerenciador de conexões [!INCLUDE[vstecado](../../includes/vstecado-md.md)] ao pacote.</span><span class="sxs-lookup"><span data-stu-id="081c9-162">Add an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager to the package.</span></span> <span data-ttu-id="081c9-163">Configure esse gerenciador de conexões para usar o Provedor de Dados NET para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) e conecte-o a uma instância disponível do banco de dados [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="081c9-163">Configure this connection manager to use the NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) and to connect to an available instance of the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span>  
  
     <span data-ttu-id="081c9-164">Por padrão, o gerenciador de conexões tem o seguinte nome: \<server name>.AdventureWorks1.</span><span class="sxs-lookup"><span data-stu-id="081c9-164">By default, the connection manager has the following name: \<server name>.AdventureWorks1.</span></span>  
  
3.  <span data-ttu-id="081c9-165">Adicione um gerenciador de conexões de arquivos ao pacote.</span><span class="sxs-lookup"><span data-stu-id="081c9-165">Add a File connection manager to the package.</span></span> <span data-ttu-id="081c9-166">Configure esse gerenciador de conexões para criar o arquivo de saída para a tarefa Criação de Perfil de Dados.</span><span class="sxs-lookup"><span data-stu-id="081c9-166">Configure this connection manager to create the output file for the Data Profiling task.</span></span>  
  
     <span data-ttu-id="081c9-167">Este exemplo usa o nome de arquivo DataProfile1.xml.</span><span class="sxs-lookup"><span data-stu-id="081c9-167">This example uses the file name, DataProfile1.xml.</span></span> <span data-ttu-id="081c9-168">Por padrão, o gerenciador de conexões tem o mesmo nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="081c9-168">By default, the connection manager has the same name as the file.</span></span>  
  
### <a name="configure-the-package-variables"></a><span data-ttu-id="081c9-169">Configure as variáveis de pacote</span><span class="sxs-lookup"><span data-stu-id="081c9-169">Configure the Package Variables</span></span>  
 <span data-ttu-id="081c9-170">Este exemplo usa duas variáveis de pacote:</span><span class="sxs-lookup"><span data-stu-id="081c9-170">This example uses two package variables:</span></span>  
  
-   <span data-ttu-id="081c9-171">A variável ProfileConnectionName passa o nome do gerenciador de conexões de arquivos para a tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="081c9-171">The ProfileConnectionName variable passes the name of the File connection manager to the Script task.</span></span>  
  
-   <span data-ttu-id="081c9-172">A variável AddressLine2NullRatio retira a razão nula calculada para esta coluna da tarefa Script do pacote.</span><span class="sxs-lookup"><span data-stu-id="081c9-172">The AddressLine2NullRatio variable passes the calculated null ratio for this column out of the Script task to the package.</span></span>  
  
##### <a name="to-configure-the-package-variables-that-will-hold-profile-results"></a><span data-ttu-id="081c9-173">Para configurar as variáveis de pacote que armazenarão os resultados de perfil</span><span class="sxs-lookup"><span data-stu-id="081c9-173">To configure the package variables that will hold profile results</span></span>  
  
-   <span data-ttu-id="081c9-174">Na janela **Variáveis** , adicione e configure as duas seguintes variáveis de pacote:</span><span class="sxs-lookup"><span data-stu-id="081c9-174">In the **Variables** window, add and configure the following two package variables:</span></span>  
  
    -   <span data-ttu-id="081c9-175">Insira o nome, `ProfileConnectionName` , para uma das variáveis e defina o tipo dessa variável como **String**.</span><span class="sxs-lookup"><span data-stu-id="081c9-175">Enter the name, `ProfileConnectionName`, for one of the variables and set the type of this variable to **String**.</span></span>  
  
    -   <span data-ttu-id="081c9-176">Insira o nome, `AddressLine2NullRatio` , para a outra variável e defina o tipo dessa variável como **Double**.</span><span class="sxs-lookup"><span data-stu-id="081c9-176">Enter the name, `AddressLine2NullRatio`, for the other variable and set the type of this variable to **Double**.</span></span>  
  
### <a name="configure-the-data-profiling-task"></a><span data-ttu-id="081c9-177">Configurar a tarefa Criação de Perfil de Dados</span><span class="sxs-lookup"><span data-stu-id="081c9-177">Configure the Data Profiling Task</span></span>  
 <span data-ttu-id="081c9-178">A tarefa Criação de Perfil de Dados deve ser configurada do seguinte modo:</span><span class="sxs-lookup"><span data-stu-id="081c9-178">The Data Profiling task has to be configured in the following way:</span></span>  
  
-   <span data-ttu-id="081c9-179">Para usar os dados fornecidos pelo gerenciador de conexões [!INCLUDE[vstecado](../../includes/vstecado-md.md)] como entrada.</span><span class="sxs-lookup"><span data-stu-id="081c9-179">To use the data that the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager supplies as input.</span></span>  
  
-   <span data-ttu-id="081c9-180">Para executar um Perfil de Razão Nula de Coluna nos dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="081c9-180">To perform a Column Null Ratio profile on the input data.</span></span>  
  
-   <span data-ttu-id="081c9-181">Para salvar os resultados de perfil no arquivo que é associado ao gerenciador de conexões de arquivos.</span><span class="sxs-lookup"><span data-stu-id="081c9-181">To save the profile results to the file that is associated with the File connection manager.</span></span>  
  
##### <a name="to-configure-the-data-profiling-task"></a><span data-ttu-id="081c9-182">Para configurar a tarefa Criação de Perfil de Dados</span><span class="sxs-lookup"><span data-stu-id="081c9-182">To configure the Data Profiling task</span></span>  
  
1.  <span data-ttu-id="081c9-183">Para o Fluxo de Controle, adicione uma tarefa Criação de Perfil de Dados.</span><span class="sxs-lookup"><span data-stu-id="081c9-183">To the Control Flow, add a Data Profiling task.</span></span>  
  
2.  <span data-ttu-id="081c9-184">Abra o **Editor de Tarefa Criação de Perfil de Dados** para configurar a tarefa.</span><span class="sxs-lookup"><span data-stu-id="081c9-184">Open the **Data Profiling Task Editor** to configure the task.</span></span>  
  
3.  <span data-ttu-id="081c9-185">Na página **Geral** do editor, para **Destino**, selecione o nome do gerenciador de conexões de arquivos configurado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="081c9-185">On the **General** page of the editor, for **Destination**, select the name of the File connection manager that you have previously configured.</span></span>  
  
4.  <span data-ttu-id="081c9-186">Na página **Solicitações de Perfil** do editor, crie um novo Perfil de Razão Nula de Coluna.</span><span class="sxs-lookup"><span data-stu-id="081c9-186">On the **Profile Requests** page of the editor, create a new Column Null Ratio Profile.</span></span>  
  
5.  <span data-ttu-id="081c9-187">No painel **Propriedades da solicitação** , para **ConnectionManager**, selecione o gerenciador de conexões do [!INCLUDE[vstecado](../../includes/vstecado-md.md)] configurado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="081c9-187">In the **Request properties** pane, for **ConnectionManager**, select the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that you have previously configured.</span></span> <span data-ttu-id="081c9-188">Em seguida, para **TableOrView**, selecione Person.Address.</span><span class="sxs-lookup"><span data-stu-id="081c9-188">Then, for **TableOrView**, select Person.Address.</span></span>  
  
6.  <span data-ttu-id="081c9-189">Feche o Editor de Tarefa Criação de Perfil de Dados.</span><span class="sxs-lookup"><span data-stu-id="081c9-189">Close the Data Profiling Task Editor.</span></span>  
  
### <a name="configure-the-script-task"></a><span data-ttu-id="081c9-190">Configurar a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="081c9-190">Configure the Script Task</span></span>  
 <span data-ttu-id="081c9-191">A tarefa Script deve ser configurada para recuperar os resultados do arquivo de saída e preencher as variáveis de pacote que foram configuradas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="081c9-191">The Script task has to be configured to retrieve the results from the output file and populate the package variables that were previously configured.</span></span>  
  
##### <a name="to-configure-the-script-task"></a><span data-ttu-id="081c9-192">Para configurar a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="081c9-192">To configure the Script task</span></span>  
  
1.  <span data-ttu-id="081c9-193">Para o Fluxo de Controle, adicione uma tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="081c9-193">To the Control Flow, add a Script task.</span></span>  
  
2.  <span data-ttu-id="081c9-194">Conecte a tarefa Script à tarefa Criação de Perfil de Dados.</span><span class="sxs-lookup"><span data-stu-id="081c9-194">Connect the Script task to the Data Profiling task.</span></span>  
  
3.  <span data-ttu-id="081c9-195">Abra o **Editor da Tarefa Script** para configurar a tarefa.</span><span class="sxs-lookup"><span data-stu-id="081c9-195">Open the **Script Task Editor** to configure the task.</span></span>  
  
4.  <span data-ttu-id="081c9-196">Na página **Script** , selecione a linguagem de programação desejada.</span><span class="sxs-lookup"><span data-stu-id="081c9-196">On the **Script** page, select your preferred programming language.</span></span> <span data-ttu-id="081c9-197">Em seguida, disponibilize as duas variáveis de pacote para o script:</span><span class="sxs-lookup"><span data-stu-id="081c9-197">Then, make the two package variables available to the script:</span></span>  
  
    1.  <span data-ttu-id="081c9-198">Para `ReadOnlyVariables` , selecione `ProfileConnectionName` .</span><span class="sxs-lookup"><span data-stu-id="081c9-198">For `ReadOnlyVariables`, select `ProfileConnectionName`.</span></span>  
  
    2.  <span data-ttu-id="081c9-199">Para **ReadWriteVariables**, selecione `AddressLine2NullRatio` .</span><span class="sxs-lookup"><span data-stu-id="081c9-199">For **ReadWriteVariables**, select `AddressLine2NullRatio`.</span></span>  
  
5.  <span data-ttu-id="081c9-200">Selecione **Editar Script** para abrir o ambiente de desenvolvimento de script.</span><span class="sxs-lookup"><span data-stu-id="081c9-200">Select **Edit Script** to open the script development environment.</span></span>  
  
6.  <span data-ttu-id="081c9-201">Adicione uma referência ao namespace System.Xml.</span><span class="sxs-lookup"><span data-stu-id="081c9-201">Add a reference to the System.Xml namespace.</span></span>  
  
7.  <span data-ttu-id="081c9-202">Insira o código de amostra que corresponde à sua linguagem de programação:</span><span class="sxs-lookup"><span data-stu-id="081c9-202">Enter the sample code that corresponds to your programming language:</span></span>  
  
    ```vb  
    Imports System  
    Imports Microsoft.SqlServer.Dts.Runtime  
    Imports System.Xml  
  
    Public Class ScriptMain  
  
      Private FILENAME As String = "C:\ TEMP\DataProfile1.xml"  
      Private PROFILE_NAMESPACE_URI As String = "https://schemas.microsoft.com/DataDebugger/"  
      Private NULLCOUNT_XPATH As String = _  
        "/default:DataProfile/default:DataProfileOutput/default:Profiles" & _  
        "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:NullCount/text()"  
      Private TABLE_XPATH As String = _  
        "/default:DataProfile/default:DataProfileOutput/default:Profiles" & _  
        "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:Table"  
  
      Public Sub Main()  
  
        Dim profileConnectionName As String  
        Dim profilePath As String  
        Dim profileOutput As New XmlDocument  
        Dim profileNSM As XmlNamespaceManager  
        Dim nullCountNode As XmlNode  
        Dim nullCount As Integer  
        Dim tableNode As XmlNode  
        Dim rowCount As Integer  
        Dim nullRatio As Double  
  
        ' Open output file.  
        profileConnectionName = Dts.Variables("ProfileConnectionName").Value.ToString()  
        profilePath = Dts.Connections(profileConnectionName).ConnectionString  
        profileOutput.Load(profilePath)  
        profileNSM = New XmlNamespaceManager(profileOutput.NameTable)  
        profileNSM.AddNamespace("default", PROFILE_NAMESPACE_URI)  
  
        ' Get null count for column.  
        nullCountNode = profileOutput.SelectSingleNode(NULLCOUNT_XPATH, profileNSM)  
        nullCount = CType(nullCountNode.Value, Integer)  
  
        ' Get row count for table.  
        tableNode = profileOutput.SelectSingleNode(TABLE_XPATH, profileNSM)  
        rowCount = CType(tableNode.Attributes("RowCount").Value, Integer)  
  
        ' Compute and return null ratio.  
        nullRatio = nullCount / rowCount  
        Dts.Variables("AddressLine2NullRatio").Value = nullRatio  
  
        Dts.TaskResult = Dts.Results.Success  
  
      End Sub  
  
    End Class  
    ```  
  
    ```csharp  
    using System;  
    using Microsoft.SqlServer.Dts.Runtime;  
    using System.Xml;  
  
    public class ScriptMain  
    {  
  
      private string FILENAME = "C:\\ TEMP\\DataProfile1.xml";  
      private string PROFILE_NAMESPACE_URI = "https://schemas.microsoft.com/DataDebugger/";  
      private string NULLCOUNT_XPATH = "/default:DataProfile/default:DataProfileOutput/default:Profiles" + "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:NullCount/text()";  
      private string TABLE_XPATH = "/default:DataProfile/default:DataProfileOutput/default:Profiles" + "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:Table";  
  
      public void Main()  
      {  
  
        string profileConnectionName;  
        string profilePath;  
        XmlDocument profileOutput = new XmlDocument();  
        XmlNamespaceManager profileNSM;  
        XmlNode nullCountNode;  
        int nullCount;  
        XmlNode tableNode;  
        int rowCount;  
        double nullRatio;  
  
        // Open output file.  
        profileConnectionName = Dts.Variables["ProfileConnectionName"].Value.ToString();  
        profilePath = Dts.Connections[profileConnectionName].ConnectionString;  
        profileOutput.Load(profilePath);  
        profileNSM = new XmlNamespaceManager(profileOutput.NameTable);  
        profileNSM.AddNamespace("default", PROFILE_NAMESPACE_URI);  
  
        // Get null count for column.  
        nullCountNode = profileOutput.SelectSingleNode(NULLCOUNT_XPATH, profileNSM);  
        nullCount = (int)nullCountNode.Value;  
  
        // Get row count for table.  
        tableNode = profileOutput.SelectSingleNode(TABLE_XPATH, profileNSM);  
        rowCount = (int)tableNode.Attributes["RowCount"].Value;  
  
        // Compute and return null ratio.  
        nullRatio = nullCount / rowCount;  
        Dts.Variables["AddressLine2NullRatio"].Value = nullRatio;  
  
        Dts.TaskResult = Dts.Results.Success;  
  
      }  
  
    }  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="081c9-203">O código de amostra exibido neste procedimento demonstra como carregar a saída da tarefa Criação de Perfil de Dados de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="081c9-203">The sample code shown in this procedure demonstrates how to load the output of the Data Profiling task from a file.</span></span> <span data-ttu-id="081c9-204">Para carregar a saída da tarefa Criação de Perfil de Dados a partir de uma variável de pacote, veja o código de amostra alternativo exibido depois desse procedimento.</span><span class="sxs-lookup"><span data-stu-id="081c9-204">To load the output of the Data Profiling task from a package variable instead, see the alternative sample code that follows this procedure.</span></span>  
  
8.  <span data-ttu-id="081c9-205">Feche o ambiente de desenvolvimento de script e, em seguida, o Editor da Tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="081c9-205">Close the script development environment, and then close the Script Task Editor.</span></span>  
  
#### <a name="alternative-code-reading-the-profile-output-from-a-variable"></a><span data-ttu-id="081c9-206">Código alternativo – Lendo a saída de perfil com base em uma variável</span><span class="sxs-lookup"><span data-stu-id="081c9-206">Alternative Code-Reading the Profile Output from a Variable</span></span>  
 <span data-ttu-id="081c9-207">O procedimento anterior mostra como carregar a saída da tarefa Criação de Perfil de Dados com base em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="081c9-207">The previous procedure shows how to load the output of the Data Profiling task from a file.</span></span> <span data-ttu-id="081c9-208">No entanto, como método alternativo, você pode carregar essa saída a partir de uma variável de pacote.</span><span class="sxs-lookup"><span data-stu-id="081c9-208">However, an alternative method would be to load this output from a package variable.</span></span> <span data-ttu-id="081c9-209">Para carregar a saída a partir de uma variável, faça as seguintes alterações no código de amostra:</span><span class="sxs-lookup"><span data-stu-id="081c9-209">To load the output from a variable, you have to make the following changes to the sample code:</span></span>  
  
-   <span data-ttu-id="081c9-210">Chame o método `LoadXml` da classe `XmlDocument` em vez do método `Load`.</span><span class="sxs-lookup"><span data-stu-id="081c9-210">Call the `LoadXml` method of the `XmlDocument` class instead of the `Load` method.</span></span>  
  
-   <span data-ttu-id="081c9-211">No Editor da Tarefa Script, adicione o nome da variável de pacote que contém a saída de perfil à lista `ReadOnlyVariables` da tarefa.</span><span class="sxs-lookup"><span data-stu-id="081c9-211">In the Script Task Editor, add the name of the package variable that contains the profile output to the task's `ReadOnlyVariables` list.</span></span>  
  
-   <span data-ttu-id="081c9-212">Passe o valor de cadeia da variável ao método `LoadXML`, como mostra o código de exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="081c9-212">Pass the string value of the variable to the `LoadXML` method, as shown in the following code example.</span></span> <span data-ttu-id="081c9-213">(Este exemplo usa “ProfileOutput” como o nome da variável de pacote que contém a saída de perfil.)</span><span class="sxs-lookup"><span data-stu-id="081c9-213">(This example uses "ProfileOutput" as the name of the package variable that contains the profile output.)</span></span>  
  
    ```vb  
    Dim outputString As String  
    outputString = Dts.Variables("ProfileOutput").Value.ToString()  
    ...  
    profileOutput.LoadXml(outputString)  
    ```  
  
    ```csharp  
    string outputString;  
    outputString = Dts.Variables["ProfileOutput"].Value.ToString();  
    ...  
    profileOutput.LoadXml(outputString);  
    ```  
  
### <a name="configure-the-precedence-constraints"></a><span data-ttu-id="081c9-214">Configurar as restrições de precedência</span><span class="sxs-lookup"><span data-stu-id="081c9-214">Configure the Precedence Constraints</span></span>  
 <span data-ttu-id="081c9-215">As restrições de precedência devem ser configuradas para controlar quais ramificações de downstream do fluxo de trabalho são executadas com base nos resultados da tarefa Criação de Perfil de Dados.</span><span class="sxs-lookup"><span data-stu-id="081c9-215">The precedence constraints have to be configured to control which downstream branches in the workflow are run based on the results of the Data Profiling task.</span></span>  
  
##### <a name="to-configure-the-precedence-constraints"></a><span data-ttu-id="081c9-216">Para configurar as restrições de precedência</span><span class="sxs-lookup"><span data-stu-id="081c9-216">To configure the precedence constraints</span></span>  
  
-   <span data-ttu-id="081c9-217">Nas restrições de precedência que conectam a tarefa Script às ramificações de downstream do fluxo de trabalho, grave expressões que usem os valores das variáveis para dirigir o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="081c9-217">In the precedence constraints that connect the Script task to downstream branches in the workflow, write expressions that use the values of the variables to direct the workflow.</span></span>  
  
     <span data-ttu-id="081c9-218">Por exemplo, você pode definir a **Operação de avaliação** da restrição de precedência como **Expressão e Restrição**.</span><span class="sxs-lookup"><span data-stu-id="081c9-218">For example, you might set the **Evaluation operation** of the precedence constraint to **Expression and Constraint**.</span></span> <span data-ttu-id="081c9-219">Em seguida, você pode usar `@AddressLine2NullRatio < .90` como o valor da expressão.</span><span class="sxs-lookup"><span data-stu-id="081c9-219">Then, you might use `@AddressLine2NullRatio < .90` as the value of the expression.</span></span> <span data-ttu-id="081c9-220">Desse modo, o fluxo de trabalho segue o caminho selecionado quando as tarefas anteriores são executadas com êxito e quando a porcentagem de valores nulos na coluna selecionada é inferior a 90%.</span><span class="sxs-lookup"><span data-stu-id="081c9-220">This causes the workflow to follow the selected path when the previous tasks succeed, and when the percentage of null values in the selected column is less than 90%.</span></span>  
  
## <a name="connecting-the-data-profiling-task-to-transformed-data-from-the-data-flow"></a><span data-ttu-id="081c9-221">Conectando a tarefa Criação de Perfil de Dados aos dados transformados do fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="081c9-221">Connecting the Data Profiling Task to Transformed Data from the Data Flow</span></span>  
 <span data-ttu-id="081c9-222">Em vez de criar um perfil de dados diretamente a partir de uma fonte de dados, você pode salvar os dados que já tenham sido carregados e transformados no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="081c9-222">Instead of profiling data directly from a data source, you can profile data that has already been loaded and transformed in the data flow.</span></span> <span data-ttu-id="081c9-223">No entanto, a tarefa Criação de Perfil de Dados funciona somente com dados persistidos, não com dados da memória.</span><span class="sxs-lookup"><span data-stu-id="081c9-223">However, the Data Profiling task works only against persisted data, not against in-memory data.</span></span> <span data-ttu-id="081c9-224">Portanto, você deve primeiro usar um componente de destino para salvar os dados transformados em uma tabela de preparação.</span><span class="sxs-lookup"><span data-stu-id="081c9-224">Therefore, you must first use a destination component to save the transformed data to a staging table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="081c9-225">Ao configurar a tarefa Criação de Perfil de Dados, é necessário selecionar tabelas e colunas existentes.</span><span class="sxs-lookup"><span data-stu-id="081c9-225">When you configure the Data Profiling task, you have to select existing tables and columns.</span></span> <span data-ttu-id="081c9-226">Portanto, você deve criar a tabela de preparação em tempo de design antes de configurar a tarefa.</span><span class="sxs-lookup"><span data-stu-id="081c9-226">Therefore, you must create the staging table at design time before you can configure the task.</span></span> <span data-ttu-id="081c9-227">Em outras palavras, esse cenário não permite o uso de uma tabela temporária criada em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="081c9-227">In other words, this scenario does not allow you to use a temporary table that is created at run time.</span></span>  
  
 <span data-ttu-id="081c9-228">Depois de salvar os dados em uma tabela de preparação, você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="081c9-228">After saving the data to a staging table, you can do the following actions:</span></span>  
  
-   <span data-ttu-id="081c9-229">Usar a tarefa Criação de Perfil de Dados para criar perfis de dados.</span><span class="sxs-lookup"><span data-stu-id="081c9-229">Use the Data Profiling task to profile the data.</span></span>  
  
-   <span data-ttu-id="081c9-230">Usar uma tarefa Script para ler os resultados conforme descrito anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="081c9-230">Use a Script task to read the results as described earlier in this topic.</span></span>  
  
-   <span data-ttu-id="081c9-231">Usar esses resultados para dirigir o fluxo de trabalho subsequente do pacote.</span><span class="sxs-lookup"><span data-stu-id="081c9-231">Use those results to direct the subsequent workflow of the package.</span></span>  
  
 <span data-ttu-id="081c9-232">O procedimento a seguir fornece a abordagem geral de uso da tarefa Criação de Perfil de Dados para criar perfis dos dados que foram transformados pelo fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="081c9-232">The following procedure provides the general approach for using the Data Profiling task to profile data that has been transformed by the data flow.</span></span> <span data-ttu-id="081c9-233">Muitas etapas são similares às descritas anteriormente para criar perfis de dados oriundos diretamente de uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="081c9-233">Many of these steps are similar to the ones described earlier for profiling data that comes directly from an external data source.</span></span> <span data-ttu-id="081c9-234">Consulte as etapas anteriores se desejar obter mais informações sobre como configurar os diversos componentes.</span><span class="sxs-lookup"><span data-stu-id="081c9-234">You might want to review those earlier steps for more information about how to configure the various components.</span></span>  
  
#### <a name="to-use-the-data-profiling-task-in-the-data-flow"></a><span data-ttu-id="081c9-235">Para usar a tarefa Criação de Perfil de Dados no fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="081c9-235">To use the Data Profiling task in the data flow</span></span>  
  
1.  <span data-ttu-id="081c9-236">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], crie um pacote.</span><span class="sxs-lookup"><span data-stu-id="081c9-236">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create a package.</span></span>  
  
2.  <span data-ttu-id="081c9-237">No Fluxo de Dados, adicione, configure e conecte as origens e transformações adequadas.</span><span class="sxs-lookup"><span data-stu-id="081c9-237">In the Data Flow, add, configure, and connect the appropriate sources and transformations.</span></span>  
  
3.  <span data-ttu-id="081c9-238">No Fluxo de Dados, adicione, configure e conecte um componente de destino que salva os dados transformados em uma tabela de preparação.</span><span class="sxs-lookup"><span data-stu-id="081c9-238">In the Data Flow, add, configure, and connect a destination component that saves the transformed data to a staging table.</span></span>  
  
4.  <span data-ttu-id="081c9-239">No Fluxo de Controle, adicione e configure uma tarefa Criação de Perfil de Dados que calcule os perfis desejados para os dados transformados na tabela de preparação.</span><span class="sxs-lookup"><span data-stu-id="081c9-239">In the Control Flow, add and configure a Data Profiling task that computes the desired profiles against the transformed data in the staging table.</span></span> <span data-ttu-id="081c9-240">Conecte a tarefa Criação de Perfil de Dados à tarefa Fluxo de Dados.</span><span class="sxs-lookup"><span data-stu-id="081c9-240">Connect the Data Profiling task to the Data Flow task.</span></span>  
  
5.  <span data-ttu-id="081c9-241">Configure as variáveis de pacote para manter os valores que deseja recuperar dos resultados de perfil.</span><span class="sxs-lookup"><span data-stu-id="081c9-241">Configure package variables to hold the values that you want to retrieve from the profile results.</span></span>  
  
6.  <span data-ttu-id="081c9-242">Adicione e configure uma tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="081c9-242">Add and configure a Script task.</span></span> <span data-ttu-id="081c9-243">Conecte a tarefa Script à tarefa Criação de Perfil de Dados.</span><span class="sxs-lookup"><span data-stu-id="081c9-243">Connect the Script task to the Data Profiling task.</span></span> <span data-ttu-id="081c9-244">Na tarefa Script, grave o código que lê os valores desejados da saída da tarefa Criação de Perfil de Dados e preencha as variáveis de pacote.</span><span class="sxs-lookup"><span data-stu-id="081c9-244">In the Script task, write code that reads the desired values from the output of the Data Profiling task and populates the package variables.</span></span>  
  
7.  <span data-ttu-id="081c9-245">Nas restrições de precedência que conectam a tarefa Script às ramificações de downstream do fluxo de trabalho, grave expressões que usem os valores das variáveis para dirigir o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="081c9-245">In the precedence constraints that connect the Script task to downstream branches in the workflow, write expressions that use the values of the variables to direct the workflow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="081c9-246">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="081c9-246">See Also</span></span>  
 <span data-ttu-id="081c9-247">[Configuração da tarefa Criação de Perfil de Dados](data-profiling-task.md) </span><span class="sxs-lookup"><span data-stu-id="081c9-247">[Setup of the Data Profiling Task](data-profiling-task.md) </span></span>  
 [<span data-ttu-id="081c9-248">Visualizador de Perfil de Dados</span><span class="sxs-lookup"><span data-stu-id="081c9-248">Data Profile Viewer</span></span>](data-profile-viewer.md)  
  
  
