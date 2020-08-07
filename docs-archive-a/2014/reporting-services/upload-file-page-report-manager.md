---
title: Página carregar arquivo (Report Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7bb3166f-9374-4449-b66a-ffb77298507d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: de03c6c6bd03cbe083d5e1edfd320264d2cc3bde
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682072"
---
# <a name="upload-file-page-report-manager"></a><span data-ttu-id="39852-102">Página Carregar Arquivo (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="39852-102">Upload File Page (Report Manager)</span></span>
  <span data-ttu-id="39852-103">Use a página Carregar Arquivo para publicar um arquivo do sistema de arquivos no banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="39852-103">Use the Upload File page to publish a file from the file system into the report server database.</span></span> <span data-ttu-id="39852-104">Arquivos carregados são representados como itens na hierarquia de pasta de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="39852-104">Uploaded files are represented as items in the report server folder hierarchy.</span></span>  
  
-   <span data-ttu-id="39852-105">Arquivos .rdl carregados são publicados em um servidor de relatório como relatórios.</span><span class="sxs-lookup"><span data-stu-id="39852-105">Uploaded .rdl files are published to a report server as reports.</span></span>  
  
-   <span data-ttu-id="39852-106">Arquivos .smdl carregados são publicados como modelos de relatório se contiverem informações de exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="39852-106">Uploaded .smdl files are published as report models if they contain data source view information.</span></span> <span data-ttu-id="39852-107">Se não tiverem uma referência de exibição da fonte de dados, um erro ocorrerá durante o carregamento.</span><span class="sxs-lookup"><span data-stu-id="39852-107">If they are missing a data source view reference, an error occurs during the upload.</span></span> <span data-ttu-id="39852-108">As informações de exibição da fonte de dados podem estar ausentes se você carregar um arquivo. smdl de um [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] projeto de modelo de relatório.</span><span class="sxs-lookup"><span data-stu-id="39852-108">Data source view information might be missing if you upload an .smdl file from a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] report model project.</span></span> <span data-ttu-id="39852-109">Nos projetos de modelo de relatório, informações de exibição da fonte de dados são armazenadas em um arquivo separado e não no próprio arquivo .smdl.</span><span class="sxs-lookup"><span data-stu-id="39852-109">In report model projects, data source view information is stored in a separate file rather than in the .smdl file itself.</span></span>  
  
     <span data-ttu-id="39852-110">Arquivos de modelo que não contêm informações de exibição da fonte de dados (e podem, portanto, ser carregados com êxito) são aqueles que foram publicados anteriormente em um servidor de relatórios e salvos em um arquivo do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="39852-110">Model files that do contain data source view information (and can therefore be successfully uploaded) are those that have been previously published to a report server and then saved from the server to a file on the file system.</span></span> <span data-ttu-id="39852-111">Se você abrir a página Propriedades Gerais de um modelo e clicar em **Editar** para abrir o modelo, poderá salvá-lo em um arquivo e carregá-lo como um novo modelo no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="39852-111">If you open the General Properties page of a model and click **Edit** to open the model, you can save it to a file and then upload it as a new model on the report server.</span></span> <span data-ttu-id="39852-112">O arquivo .smdl carregado subsequentemente terá todas as informações necessárias para a publicação do modelo.</span><span class="sxs-lookup"><span data-stu-id="39852-112">The .smdl file that you subsequently upload will have all of information that is necessary for model publication.</span></span>  
  
-   <span data-ttu-id="39852-113">Todos os outros tipos de arquivo que você carrega são armazenados como recursos.</span><span class="sxs-lookup"><span data-stu-id="39852-113">All other file types that you upload are stored as resources.</span></span> <span data-ttu-id="39852-114">Isso inclui arquivos .rds que contêm informações de conexão da fonte de dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="39852-114">This includes .rds files that contain report data source connection information.</span></span> <span data-ttu-id="39852-115">O carregamento de um arquivo .rds não produz um item da fonte de dados compartilhada no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="39852-115">Uploading an .rds file does not produce a shared data source item on the report server.</span></span>  
  
 <span data-ttu-id="39852-116">Quando você carrega um item, ele é colocado na pasta atual.</span><span class="sxs-lookup"><span data-stu-id="39852-116">When you upload an item, it is placed in the current folder.</span></span> <span data-ttu-id="39852-117">Quando o carregamento estiver concluído, você poderá mover o item para outro local.</span><span class="sxs-lookup"><span data-stu-id="39852-117">After the upload is complete, you can move the item to a different location.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="39852-118">Este recurso não está disponível em todas as edições do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39852-118">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="39852-119">Para obter uma lista de recursos com suporte nas edições do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], consulte [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="39852-119">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="39852-120">Navegação</span><span class="sxs-lookup"><span data-stu-id="39852-120">Navigation</span></span>  
 <span data-ttu-id="39852-121">Use o procedimento a seguir para navegar para este local na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="39852-121">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-upload-file-page"></a><span data-ttu-id="39852-122">Para abrir a página Carregar Arquivo</span><span class="sxs-lookup"><span data-stu-id="39852-122">To open the Upload File page</span></span>  
  
1.  <span data-ttu-id="39852-123">Abra o Gerenciador de Relatórios e navegue até a pasta na qual você deseja carregar um arquivo.</span><span class="sxs-lookup"><span data-stu-id="39852-123">Open Report Manager, and navigate to the folder in which you want to upload a file.</span></span>  
  
2.  <span data-ttu-id="39852-124">Na barra de ferramentas, clique em **Carregar Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="39852-124">In the toolbar, click **Upload File**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="39852-125">Opções</span><span class="sxs-lookup"><span data-stu-id="39852-125">Options</span></span>  
 <span data-ttu-id="39852-126">**Arquivo a ser Carregado**</span><span class="sxs-lookup"><span data-stu-id="39852-126">**File to Upload**</span></span>  
 <span data-ttu-id="39852-127">Exibe o caminho totalmente qualificado do arquivo que você está copiando do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="39852-127">Displays the fully qualified path to the file you are copying from the file system.</span></span>  
  
 <span data-ttu-id="39852-128">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="39852-128">**Browse**</span></span>  
 <span data-ttu-id="39852-129">Clique para escolher um arquivo do sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="39852-129">Click to choose a file from the file system.</span></span>  
  
 <span data-ttu-id="39852-130">**Nome**</span><span class="sxs-lookup"><span data-stu-id="39852-130">**Name**</span></span>  
 <span data-ttu-id="39852-131">Digite o nome do arquivo como ele aparecerá no namespace do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="39852-131">Type the name of the file, as it will appear in the report server namespace.</span></span> <span data-ttu-id="39852-132">Um nome deve conter pelo menos um caractere alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="39852-132">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="39852-133">Também pode conter espaços e certos símbolos.</span><span class="sxs-lookup"><span data-stu-id="39852-133">It can also include spaces and certain symbols.</span></span> <span data-ttu-id="39852-134">Não use os caracteres ; ?</span><span class="sxs-lookup"><span data-stu-id="39852-134">Do not use the characters ; ?</span></span> <span data-ttu-id="39852-135">: \@ & = +, $ \* \< > | "ou/ao especificar um nome de item.</span><span class="sxs-lookup"><span data-stu-id="39852-135">: \@ & = + , $ \* \< > | " or / when specifying an item name.</span></span>  
  
 <span data-ttu-id="39852-136">**Substituir item, se existir**</span><span class="sxs-lookup"><span data-stu-id="39852-136">**Overwrite item if it exists**</span></span>  
 <span data-ttu-id="39852-137">Marque esta caixa de seleção se você quiser substituir um item existente por uma versão mais nova.</span><span class="sxs-lookup"><span data-stu-id="39852-137">Select this check box if you want to replace an existing item with a newer version.</span></span> <span data-ttu-id="39852-138">Para substituir uma versão existente, o nome do novo item e o item existente devem corresponder exatamente.</span><span class="sxs-lookup"><span data-stu-id="39852-138">To overwrite an existing version, the name of the new item and the existing item must be an exact match.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39852-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="39852-139">See Also</span></span>  
 <span data-ttu-id="39852-140">[Gerenciador de Relatórios &#40;Modo Nativo do SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="39852-140">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="39852-141">[Página de conteúdo &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="39852-141">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="39852-142">[Ajuda F1 Report Manager](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="39852-142">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 [<span data-ttu-id="39852-143">Carregar arquivos em uma pasta</span><span class="sxs-lookup"><span data-stu-id="39852-143">Upload Files to a Folder</span></span>](report-server/upload-files-to-a-folder.md)  
  
  
