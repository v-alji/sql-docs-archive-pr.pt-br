---
title: 'Etapa 4: implantar o pacote da Lição 6 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b613cef7-7993-4d89-a429-a8251d74d435
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8c5109dc96af138bbd0c8c0087e8b73cf3bac435
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583731"
---
# <a name="step-4-deploying-the-lesson-6-package"></a><span data-ttu-id="09140-102">Etapa 4: Implantar o pacote da Lição 6</span><span class="sxs-lookup"><span data-stu-id="09140-102">Step 4: Deploying the Lesson 6 Package</span></span>
  <span data-ttu-id="09140-103">Implantar o pacote envolve a adição do pacote no catálogo de SSISDB nos Integration Services em uma instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="09140-103">Deploying the package involves adding the package to the SSISDB catalog in Integration Services on an instance of SQL Server.</span></span> <span data-ttu-id="09140-104">Nesta lição, você adicionará o pacote da Lição 6 no catálogo SSISDB, definirá o parâmetro e executará o pacote.</span><span class="sxs-lookup"><span data-stu-id="09140-104">In this lesson you will add the Lesson 6 package to the SSISDB catalog, set the parameter, and execute the package.</span></span> <span data-ttu-id="09140-105">Nesta lição você usará o SQL Server Management Studio para adicionar o pacote da Lição 6 ao catálogo SSISDB e implantará esse pacote.</span><span class="sxs-lookup"><span data-stu-id="09140-105">For this lesson you will use SQL Server Management Studio to add the Lesson 6 package to the SSISDB catalog, and deploy the package.</span></span> <span data-ttu-id="09140-106">Depois de implantar o pacote, você modificará o parâmetro para apontar para um novo local e, em seguida, executará o pacote.</span><span class="sxs-lookup"><span data-stu-id="09140-106">After deploying the package you will modify the parameter to point to a new location then execute the package.</span></span>  
  
 <span data-ttu-id="09140-107">Nesta lição, você irá:</span><span class="sxs-lookup"><span data-stu-id="09140-107">In this lesson you will:</span></span>  
  
-   <span data-ttu-id="09140-108">Adicionar o pacote ao catálogo de SSISDB no nó SSIS no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="09140-108">Add the package to the SSISDB catalog in the SSIS node in SQL Server.</span></span>  
  
-   <span data-ttu-id="09140-109">Implantar o pacote.</span><span class="sxs-lookup"><span data-stu-id="09140-109">Deploy the package.</span></span>  
  
-   <span data-ttu-id="09140-110">Definir o valor de parâmetro do pacote.</span><span class="sxs-lookup"><span data-stu-id="09140-110">Set the package parameter value.</span></span>  
  
-   <span data-ttu-id="09140-111">Executar o pacote no SSMS.</span><span class="sxs-lookup"><span data-stu-id="09140-111">Execute the package in SSMS.</span></span>  
  
### <a name="to-locate-or-add-the-ssisdb-catalog"></a><span data-ttu-id="09140-112">Para localizar ou adicionar o catálogo do SSISDB</span><span class="sxs-lookup"><span data-stu-id="09140-112">To Locate or add the SSISDB catalog</span></span>  
  
1.  <span data-ttu-id="09140-113">Clique em Iniciar, aponte para Todos os programas, aponte para Microsoft SQL Server 2012 e, em seguida, clique em SQL Management Studio.</span><span class="sxs-lookup"><span data-stu-id="09140-113">Click Start, point to All Programs, point to Microsoft SQL Server 2012, and then click SQL Management Studio.</span></span>  
  
2.  <span data-ttu-id="09140-114">Na caixa de diálogo Conectar ao Servidor, verifique as configurações padrão e depois clique em Conectar.</span><span class="sxs-lookup"><span data-stu-id="09140-114">On the Connect to Server dialog box, verify the default settings, and then click Connect.</span></span> <span data-ttu-id="09140-115">Para fazer a conexão, a caixa de diálogo Nome do servidor deve conter o nome do computador em que o SQL Server está instalado.</span><span class="sxs-lookup"><span data-stu-id="09140-115">To connect, the Server name box must contain the name of the computer where SQL Server is installed.</span></span> <span data-ttu-id="09140-116">Se o Mecanismo de Banco de Dados for uma instância nomeada, a caixa Nome do Servidor também deverá conter o nome da instância no formato <computer_name>\\<instance_name>.</span><span class="sxs-lookup"><span data-stu-id="09140-116">If the Database Engine is a named instance, the Server name box should also contain the instance name in the format <computer_name>\\<instance_name>.</span></span>  
  
3.  <span data-ttu-id="09140-117">No Pesquisador de objetos, expanda Catálogos dos Integration Services.</span><span class="sxs-lookup"><span data-stu-id="09140-117">In Object Explorer expand Integration Services Catalogs.</span></span>  
  
4.  <span data-ttu-id="09140-118">Se não houver nenhum catálogo listado em Catálogos dos Integration Services, adicione o catálogo SSISDB.</span><span class="sxs-lookup"><span data-stu-id="09140-118">If there are no catalogs listed under Integration Services Catalogs then add the SSISDB catalog.</span></span>  
  
5.  <span data-ttu-id="09140-119">Para adicionar o catálogo do SSISDB, clique com botão direito em Catálogos dos Integration Services e clique em Criar catálogo.</span><span class="sxs-lookup"><span data-stu-id="09140-119">To Add the SSISDB catalog, right-click Integration Services Catalogs and click Create Catalog.</span></span>  
  
6.  <span data-ttu-id="09140-120">Na caixa de diálogo Criar catálogo, selecione Habilitar a integração do CLR.</span><span class="sxs-lookup"><span data-stu-id="09140-120">On the Create Catalog dialog box select Enable CLR Integration.</span></span>  
  
7.  <span data-ttu-id="09140-121">Digite uma nova senha na caixa Senha; então, digite-a novamente na caixa Confirmar senha.</span><span class="sxs-lookup"><span data-stu-id="09140-121">In the Password box, type a new password then type it again in the Retype Password box.</span></span> <span data-ttu-id="09140-122">Certifique-se de lembrar a senha que você digitar.</span><span class="sxs-lookup"><span data-stu-id="09140-122">Be sure to remember the password you type.</span></span>  
  
8.  <span data-ttu-id="09140-123">Clique em OK para adicionar o catálogo SSISDB.</span><span class="sxs-lookup"><span data-stu-id="09140-123">Click OK to add the SSISDB catalog.</span></span>  
  
### <a name="to-add-the-package-to-the-ssisdb-catalog"></a><span data-ttu-id="09140-124">Para adicionar o pacote ao catálogo SSISDB</span><span class="sxs-lookup"><span data-stu-id="09140-124">To add the package to the SSISDB catalog</span></span>  
  
1.  <span data-ttu-id="09140-125">No Pesquisador de objetos, clique com o botão direito do mouse em SSISDB e clique em Criar pasta.</span><span class="sxs-lookup"><span data-stu-id="09140-125">In Object Explorer, right-click SSISDB and click Create Folder.</span></span>  
  
2.  <span data-ttu-id="09140-126">Na caixa de diálogo Criar pasta, digite Tutorial do SSIS na caixa de nome de pasta e clique em OK.</span><span class="sxs-lookup"><span data-stu-id="09140-126">In the Create Folder dialog box type SSIS Tutorial in the Folder name box and click OK.</span></span>  
  
3.  <span data-ttu-id="09140-127">Expanda a pasta Tutorial do SSIS, clique com o botão direito do mouse em Projetos e clique em Importar pacotes.</span><span class="sxs-lookup"><span data-stu-id="09140-127">Expand the SSIS Tutorial folder, right-click Projects, and click Import Packages.</span></span>  
  
4.  <span data-ttu-id="09140-128">Na página de Introdução do Assistente de conversão de projeto do Integration Services, clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="09140-128">On the Integration Services Project Conversion Wizard Introduction page click Next.</span></span>  
  
5.  <span data-ttu-id="09140-129">Na página localizar pacotes, verifique se o sistema de arquivos está selecionado na lista de origem; então, clique em Procurar.</span><span class="sxs-lookup"><span data-stu-id="09140-129">On the Locate Packages page, ensure that File system is selected in the Source list, then click Browse.</span></span>  
  
6.  <span data-ttu-id="09140-130">Na caixa de diálogo Procurar pasta, navegue até a pasta que contém o projeto do Tutorial do SSIS e clique em OK.</span><span class="sxs-lookup"><span data-stu-id="09140-130">On the Browse For Folder dialog box, browse to the folder containing the SSIS Tutorial project, then click OK.</span></span>  
  
7.  <span data-ttu-id="09140-131">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="09140-131">Click Next.</span></span>  
  
8.  <span data-ttu-id="09140-132">Na página Selecionar pacotes, você deve ver todos os seis pacotes do Tutorial do SSIS.</span><span class="sxs-lookup"><span data-stu-id="09140-132">On the Select Packages page you should see all six packages from the SSIS Tutorial.</span></span> <span data-ttu-id="09140-133">Na lista de pacotes, selecione Lição 6.dtsx e clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="09140-133">In the Packages list, select Lesson 6.dtsx, then click Next.</span></span>  
  
9. <span data-ttu-id="09140-134">Na página Selecionar destino, digite Implantação do tutorial do SSIS na caixa Nome do projeto e clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="09140-134">On the Select Destination page, type SSIS Tutorial Deployment in the Project Name box then click Next.</span></span>  
  
10. <span data-ttu-id="09140-135">Clique em Avançar em cada uma das páginas restantes do assistente até chegar à página Revisão.</span><span class="sxs-lookup"><span data-stu-id="09140-135">Click Next on each of the remaining wizard pages until you get to the Review page.</span></span>  
  
11. <span data-ttu-id="09140-136">Na página Revisão, clique em Converter.</span><span class="sxs-lookup"><span data-stu-id="09140-136">On the Review page, click Convert.</span></span>  
  
12. <span data-ttu-id="09140-137">Quando a conversão for concluída, clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="09140-137">When the conversion completes, click Close.</span></span>  
  
 <span data-ttu-id="09140-138">Quando você fecha o Assistente de conversão de projeto do Integration Services, o SSIS exibe o Assistente de implantação do Integration Services.</span><span class="sxs-lookup"><span data-stu-id="09140-138">When you close the Integration Services Project Conversion Wizard, SSIS displays the Integration Services Deployment Wizard.</span></span> <span data-ttu-id="09140-139">Você agora usará esse assistente para implantar o pacote da Lição 6.</span><span class="sxs-lookup"><span data-stu-id="09140-139">You will use this wizard now to deploy the Lesson 6 package.</span></span>  
  
1.  <span data-ttu-id="09140-140">Na página de Introdução do Assistente de implantação do Integration Services, revise as etapas para implantação do projeto e clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="09140-140">On the Integration Services Deployment Wizard Introduction page, review the steps for deploying the project, then click Next.</span></span>  
  
2.  <span data-ttu-id="09140-141">Na página Selecionar destino, verifique se o nome do servidor é a instância do SQL Server que contém o catálogo do SSISDB e o caminho mostra o Implantação do tutorial do SSIS; então, clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="09140-141">On the Select Destination page verify that the server name is the instance of SQL Server containing the SSISDB catalog and that the path shows SSIS Tutorial Deployment, then click Next.</span></span>  
  
3.  <span data-ttu-id="09140-142">Na página Revisão, revise o resumo e clique em Implantar.</span><span class="sxs-lookup"><span data-stu-id="09140-142">On the Review page, review the Summary then click Deploy.</span></span>  
  
4.  <span data-ttu-id="09140-143">Quando a implantação for concluída, clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="09140-143">When the deployment completes, click Close.</span></span>  
  
5.  <span data-ttu-id="09140-144">No Pesquisador de objetos, clique com o botão direito do mouse em Catálogos do Integration Services e clique em Atualizar.</span><span class="sxs-lookup"><span data-stu-id="09140-144">In Object Explorer, right-click Integration Services Catalogs and click Refresh.</span></span>  
  
6.  <span data-ttu-id="09140-145">Expanda Catálogos do Integration Services e então expanda SSISDB.</span><span class="sxs-lookup"><span data-stu-id="09140-145">Expand Integration Services Catalogs then expand SSISDB.</span></span> <span data-ttu-id="09140-146">Continue a expandir a árvore sob Tutorial do SSIS até ter expandido completamente o projeto.</span><span class="sxs-lookup"><span data-stu-id="09140-146">Continue to Expand the tree under SSIS Tutorial until you have completely expanded the project.</span></span> <span data-ttu-id="09140-147">Você deve ver Lição 6.dtsx sob o nó Pacotes do nó Implantação do tutorial do SSIS.</span><span class="sxs-lookup"><span data-stu-id="09140-147">You should see Lesson 6.dtsx under the Packages node of the SSIS Tutorial Deployment node.</span></span>  
  
 <span data-ttu-id="09140-148">Para verificar se o pacote está concluído, clique com botão direito em Lição 6.dtsx e clique em Configurar.</span><span class="sxs-lookup"><span data-stu-id="09140-148">To verify that the package is complete, right-click Lesson 6.dtsx and click Configure.</span></span> <span data-ttu-id="09140-149">Na caixa de diálogo Configurar, selecione parâmetros e verifique se há uma entrada com a lição 6. dtsx como o contêiner, VarFolderName como o nome e o caminho para a pasta Novos dados de exemplo como o valor; então, clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="09140-149">On the Configure dialog box, select Parameters and verify that there is an entry with Lesson 6.dtsx as the Container, VarFolderName as the Name and the path to New Sample Data as the value, then click Close.</span></span>  
  
 <span data-ttu-id="09140-150">Antes de continuar para criar uma nova pasta de dados de exemplo, nomeie-a Dados de exemplo Dois e copie três arquivos de exemplo originais quaisquer para essa pasta.</span><span class="sxs-lookup"><span data-stu-id="09140-150">Before continuing create a new sample data folder, name it Sample Data Two, and copy any three of the original sample files into it.</span></span>  
  
### <a name="to-create-and-populate-a-new-sample-data-folder"></a><span data-ttu-id="09140-151">Para criar e popular uma nova pasta de dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="09140-151">To create and populate a new sample data folder</span></span>  
  
1.  <span data-ttu-id="09140-152">No Windows Explorer, no nível da raiz da unidade (por exemplo, C:\\), crie uma nova pasta chamada Dados de Exemplo Dois.</span><span class="sxs-lookup"><span data-stu-id="09140-152">In Windows Explorer, at the root level of your drive (for example, C:\\), create a new folder named Sample Data Two.</span></span>  
  
2.  <span data-ttu-id="09140-153">Abra a pasta C:\Program Files\Microsoft SQL Server\110\Samples\Integration Services\Tutorial\Criando Um Pacote ETL simples\Dados de Exemplo e, em seguida, copie dos três dos arquivos de exemplo contidos na pasta.</span><span class="sxs-lookup"><span data-stu-id="09140-153">Open the c:\Program Files\Microsoft SQL Server\110\Samples\Integration Services\Tutorial\Creating a Simple ETL Package\Sample Data folder and then copy any three of the sample files from the folder.</span></span>  
  
3.  <span data-ttu-id="09140-154">Na pasta Novos Dados de Exemplo, cole os arquivos copiados.</span><span class="sxs-lookup"><span data-stu-id="09140-154">In the New Sample Data folder, paste the copied files.</span></span>  
  
### <a name="to-change-the-package-parameter-to-point-to-the-new-sample-data"></a><span data-ttu-id="09140-155">Para alterar o parâmetro de pacote para apontar para os novos dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="09140-155">To change the package parameter to point to the new sample data</span></span>  
  
1.  <span data-ttu-id="09140-156">No Pesquisador de objetos, clique com botão direito em Lição 6.dtsx e clique em Configurar.</span><span class="sxs-lookup"><span data-stu-id="09140-156">In Object Explorer, right click Lesson 6.dtsx and click Configure.</span></span>  
  
2.  <span data-ttu-id="09140-157">Na caixa de diálogo Configurar, altere o valor do parâmetro para o caminho da pasta Dados de Exemplo Dois.</span><span class="sxs-lookup"><span data-stu-id="09140-157">On the Configure dialog box, change the parameter value to the path to Sample Data Two.</span></span> <span data-ttu-id="09140-158">Por exemplo, C:\Dados de Exemplo Dois se você colocou a nova pasta na raiz da unidade C.</span><span class="sxs-lookup"><span data-stu-id="09140-158">For example C:\Sample Data Two if you placed the new folder in the root folder on the C drive.</span></span>  
  
3.  <span data-ttu-id="09140-159">Clique em OK para fechar a caixa de diálogo Configurar.</span><span class="sxs-lookup"><span data-stu-id="09140-159">Click OK to close the Configure dialog box.</span></span>  
  
### <a name="to-test-the-lesson-6-package-deployment"></a><span data-ttu-id="09140-160">Para testar a implantação de pacote da Lição 6</span><span class="sxs-lookup"><span data-stu-id="09140-160">To test the Lesson 6 package deployment</span></span>  
  
1.  <span data-ttu-id="09140-161">No Pesquisador de objetos, clique com botão direito em Lição 6.dtsx e clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="09140-161">In Object Explorer, right click Lesson 6.dtsx and click Execute.</span></span>  
  
2.  <span data-ttu-id="09140-162">Na caixa de diálogo Executar pacote, clique em OK.</span><span class="sxs-lookup"><span data-stu-id="09140-162">On the Execute Package dialog box, click OK.</span></span>  
  
3.  <span data-ttu-id="09140-163">Na caixa de diálogo de mensagem, clique em Sim para abrir o Relatório de visão geral.</span><span class="sxs-lookup"><span data-stu-id="09140-163">On the message dialog box click Yes to open Overview Report.</span></span>  
  
 <span data-ttu-id="09140-164">O Relatório de visão geral do pacote será exibido, mostrando o nome do pacote e um resumo do status.</span><span class="sxs-lookup"><span data-stu-id="09140-164">The Overview report for the package is displayed showing the name of the package and a status summary.</span></span> <span data-ttu-id="09140-165">A seção Visão geral de execução mostra o resultado de cada tarefa no pacote, enquanto a seção Parâmetros usados mostra os nomes e valores de todos os parâmetros usados na execução do pacote, incluindo VarFolderName.</span><span class="sxs-lookup"><span data-stu-id="09140-165">The Execution Overview section shows the result from each task in the package and the Parameters Used section shows the names and values of all parameters used in the package execution, including VarFolderName.</span></span>  
  
  
