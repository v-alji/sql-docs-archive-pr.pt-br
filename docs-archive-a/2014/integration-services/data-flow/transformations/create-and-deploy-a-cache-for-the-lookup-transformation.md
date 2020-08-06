---
title: Criar e implantar um cache para a transformação Pesquisa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- creating cache files for Lookup transformation
- deploying cache files for Lookup transformation
- Lookup transformation cache files
ms.assetid: cedf5cad-2fac-42d0-ad91-9461e117d330
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b33b00b84f1f1448c2ee80882aedc3a330ba0a5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568704"
---
# <a name="create-and-deploy-a-cache-for-the-lookup-transformation"></a><span data-ttu-id="bb5d3-102">Criar e implantar um cache para a Transformação Pesquisa</span><span class="sxs-lookup"><span data-stu-id="bb5d3-102">Create and Deploy a Cache for the Lookup Transformation</span></span>
  <span data-ttu-id="bb5d3-103">Você pode criar e implementar um arquivo de cache (.caw) para uma transformação Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-103">You can create and deploy a cache file (.caw) for the Lookup transformation.</span></span> <span data-ttu-id="bb5d3-104">O conjunto de dados de referência é armazenado no arquivo de cache.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-104">The reference dataset is stored in the cache file.</span></span>  
  
 <span data-ttu-id="bb5d3-105">A transformação Pesquisa executa pesquisas ao unir dados em colunas de dados de uma fonte de dados conectados com colunas no conjunto de dados de referência.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-105">The Lookup transformation performs lookups by joining data in input columns from a connected data source with columns in the reference dataset.</span></span>  
  
 <span data-ttu-id="bb5d3-106">Você cria um arquivo de cache usando um gerenciador de conexões de cache e uma transformação Cache.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-106">You create a cache file by using a Cache connection manager and a Cache Transform transformation.</span></span> <span data-ttu-id="bb5d3-107">Para obter mais informações, consulte [Editor do Gerenciador de Conexões de Cache](../../connection-manager/cache-connection-manager.md) e [Transformação de Cache](cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="bb5d3-107">For more information, see [Cache Connection Manager](../../connection-manager/cache-connection-manager.md) and [Cache Transform](cache-transform.md).</span></span>  
  
 <span data-ttu-id="bb5d3-108">Para saber mais sobre a transformação Pesquisa e os arquivos de cache, consulte [Transformação Pesquisa](lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="bb5d3-108">To learn more about the Lookup transformation and cache files, see [Lookup Transformation](lookup-transformation.md).</span></span>  
  
### <a name="to-create-a-cache-file"></a><span data-ttu-id="bb5d3-109">Para criar um arquivo de cache</span><span class="sxs-lookup"><span data-stu-id="bb5d3-109">To create a cache file</span></span>  
  
1.  <span data-ttu-id="bb5d3-110">No [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] que contém o pacote que você deseja, e, então, abra o pacote.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-110">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want, and then open the package.</span></span>  
  
2.  <span data-ttu-id="bb5d3-111">Na guia **Fluxo de Controle** , adicione uma tarefa de Fluxo de Dados.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-111">On the **Control Flow** tab, add a Data Flow task.</span></span>  
  
3.  <span data-ttu-id="bb5d3-112">Na guia **Fluxo de Dados** , adicione uma transformação Cache Transform ao fluxo de dados, e, então, conecte a transformação à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-112">On the **Data Flow** tab, add a Cache Transform transformation to the data flow, and then connect the transformation to a data source.</span></span>  
  
     <span data-ttu-id="bb5d3-113">Configure a fonte de dados como necessário.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-113">Configure the data source as needed.</span></span>  
  
4.  <span data-ttu-id="bb5d3-114">Clique duas vezes na transformação Cache e, depois, em **Editor de Transformação Cache**, na página **Gerenciador de Conexões** , clique em **Novo** para criar um novo gerenciador de conexões de Cache.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-114">Double-click the Cache Transform, and then in the **Cache Transformation Editor**, on the **Connection Manager** page, click **New** to create a new Cache connection manager.</span></span>  
  
5.  <span data-ttu-id="bb5d3-115">No **Editor do Gerenciador de Conexões de Cache**, na guia **Geral** , configure o gerenciador de conexões de cache para salvar o cache selecionando as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="bb5d3-115">In the **Cache Connection Manager Editor**, on the **General** tab, configure the Cache connection manager to save the cache by selecting the following options:</span></span>  
  
    1.  <span data-ttu-id="bb5d3-116">Selecione **Usar Cache de Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-116">Select **Use file cache**.</span></span>  
  
    2.  <span data-ttu-id="bb5d3-117">Para **Nome do arquivo**, digite o caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-117">For **File name**, type the file path.</span></span>  
  
     <span data-ttu-id="bb5d3-118">O sistema cria o arquivo quando você executa o pacote.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-118">The system creates the file when you run the package.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bb5d3-119">O nível de proteção do pacote não se aplica ao arquivo de cache.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-119">The protection level of the package does not apply to the cache file.</span></span> <span data-ttu-id="bb5d3-120">Se o arquivo de cache tiver informações confidenciais, use uma lista de controle de acesso (ACL) para restringir o acesso ao local ou à pasta na qual você deseja armazenar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-120">If the cache file contains sensitive information, use an access control list (ACL) to restrict access to the location or folder in which you store the file.</span></span> <span data-ttu-id="bb5d3-121">Você deve habilitar o acesso apenas para determinadas contas.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-121">You should enable access only to certain accounts.</span></span> <span data-ttu-id="bb5d3-122">Para obter mais informações, consulte [Acesso aos arquivos usados por pacotes](../../access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="bb5d3-122">For more information, see [Access to Files Used by Packages](../../access-to-files-used-by-packages.md).</span></span>  
  
6.  <span data-ttu-id="bb5d3-123">Clique na guia **Colunas** e, então, especifique quais são as colunas de índice usando a opção **Posição do Índice** .</span><span class="sxs-lookup"><span data-stu-id="bb5d3-123">Click the **Columns** tab, and then specify which columns are the index columns by using the **Index Position** option.</span></span>  
  
     <span data-ttu-id="bb5d3-124">Para colunas sem-índice, a posição de índice é 0.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-124">For non-index columns, the index position is 0.</span></span> <span data-ttu-id="bb5d3-125">Para colunas de índice, a posição de índice é um número sequencial positivo.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-125">For index columns, the index position is a sequential, positive number.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bb5d3-126">Quando a transformação Pesquisa é configurada para usar um gerenciador de conexões de Cache, somente as colunas de índice no conjunto de dados de referência podem ser mapeadas para as colunas de entrada.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-126">When the Lookup transformation is configured to use a Cache connection manager, only index columns in the reference dataset can be mapped to input columns.</span></span> <span data-ttu-id="bb5d3-127">Além disso, todas as colunas de índice devem ser mapeadas.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-127">Also all index columns must be mapped.</span></span>  
  
     <span data-ttu-id="bb5d3-128">Para obter mais informações, consulte [Cache Connection Manager Editor](../../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="bb5d3-128">For more information, see [Cache Connection Manager Editor](../../cache-connection-manager-editor.md).</span></span>  
  
7.  <span data-ttu-id="bb5d3-129">Configure o Cache Transform como necessário.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-129">Configure the Cache Transform as needed.</span></span>  
  
     <span data-ttu-id="bb5d3-130">Para obter mais informações, consulte [Editor de Transformação Cache &#40;Página Gerenciador de Conexões&#41;](../../cache-transformation-editor-connection-manager-page.md) e [Editor de Transformação Cache &#40;Página Mapeamentos&#41;](../../cache-transformation-editor-mappings-page.md).</span><span class="sxs-lookup"><span data-stu-id="bb5d3-130">For more information, see [Cache Transformation Editor &#40;Connection Manager Page&#41;](../../cache-transformation-editor-connection-manager-page.md) and [Cache Transformation Editor &#40;Mappings Page&#41;](../../cache-transformation-editor-mappings-page.md).</span></span>  
  
8.  <span data-ttu-id="bb5d3-131">Execute o pacote.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-131">Run the package.</span></span>  
  
### <a name="to-deploy-a-cache-file"></a><span data-ttu-id="bb5d3-132">Para implementar um arquivo de cache</span><span class="sxs-lookup"><span data-stu-id="bb5d3-132">To deploy a cache file</span></span>  
  
1.  <span data-ttu-id="bb5d3-133">No [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] que contém o pacote que você deseja, e, então, abra o pacote.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-133">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want, and then open the package.</span></span>  
  
2.  <span data-ttu-id="bb5d3-134">Opcionalmente, crie uma configuração de pacote</span><span class="sxs-lookup"><span data-stu-id="bb5d3-134">Optionally, create a package configuration.</span></span> <span data-ttu-id="bb5d3-135">Para obter mais informações, consulte [Criar configurações de pacote](../../create-package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="bb5d3-135">For more information, see [Create Package Configurations](../../create-package-configurations.md).</span></span>  
  
3.  <span data-ttu-id="bb5d3-136">Adicione o arquivo de cache ao projeto fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bb5d3-136">Add the cache file to the project by doing the following:</span></span>  
  
    1.  <span data-ttu-id="bb5d3-137">No Gerenciador de Soluções, selecione o projeto que você abriu na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-137">In Solution Explorer, select the project you opened in step 1.</span></span>  
  
    2.  <span data-ttu-id="bb5d3-138">No menu **Projeto** , clique em **Item AddExisting**.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-138">On the **Project** menu, click **AddExisting Item**.</span></span>  
  
    3.  <span data-ttu-id="bb5d3-139">Selecione o arquivo de cache e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-139">Select the cache file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="bb5d3-140">O arquivo aparece na pasta **Diversos** no Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-140">The file appears in the **Miscellaneous** folder in Solution Explorer.</span></span>  
  
4.  <span data-ttu-id="bb5d3-141">Configure o projeto para criar um utilitário de implantação e, em seguida, crie o projeto.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-141">Configure the project to create a deployment utility, and then build the project.</span></span> <span data-ttu-id="bb5d3-142">Para obter mais informações, consulte [Criar um utilitário de implantação](../../create-a-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="bb5d3-142">For more information, see [Create a Deployment Utility](../../create-a-deployment-utility.md).</span></span>  
  
     <span data-ttu-id="bb5d3-143">Um arquivo de manifesto, \<*project name*>.SSISDeploymentManifest.xml, é criado e lista os arquivos diversos no projeto, os pacotes e as configurações de pacote.</span><span class="sxs-lookup"><span data-stu-id="bb5d3-143">A manifest file, \<*project name*>.SSISDeploymentManifest.xml, is created that lists the miscellaneous files in the project, the packages, and the package configurations.</span></span>  
  
5.  <span data-ttu-id="bb5d3-144">Implemente os pacotes no sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="bb5d3-144">Deploy the package to the file system.</span></span> <span data-ttu-id="bb5d3-145">Para obter mais informações, consulte [Implantar pacotes por meio do utilitário de implantação](../../deploy-packages-by-using-the-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="bb5d3-145">For more information, see [Deploy Packages by Using the Deployment Utility](../../deploy-packages-by-using-the-deployment-utility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb5d3-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bb5d3-146">See Also</span></span>  
 [<span data-ttu-id="bb5d3-147">Criar um utilitário de implantação</span><span class="sxs-lookup"><span data-stu-id="bb5d3-147">Create a Deployment Utility</span></span>](../../create-a-deployment-utility.md)  
  
  
