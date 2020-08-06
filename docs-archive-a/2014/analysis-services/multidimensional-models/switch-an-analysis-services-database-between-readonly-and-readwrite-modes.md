---
title: Alternar um banco de dados Analysis Services entre os modos ReadOnly e ReadWrite | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- ReadOnly property
- ReadWriteMode command
- operations [Analysis Services - multidimensional data]
ms.assetid: 4eff8181-08dd-4fad-b091-d400fc21a020
author: minewiskan
ms.author: owend
ms.openlocfilehash: 757aedd985d969f932deacf5599716078021a1af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678311"
---
# <a name="switch-an-analysis-services-database-between-readonly-and-readwrite-modes"></a><span data-ttu-id="b2d76-102">Alternar um banco de dados do Analysis Services entre os modos ReadOnly e ReadWrite</span><span class="sxs-lookup"><span data-stu-id="b2d76-102">Switch an Analysis Services database between ReadOnly and ReadWrite modes</span></span>
  <span data-ttu-id="b2d76-103">Frequentemente, há situações quando um administrador de banco de dados [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] (dba) quer alterar o modo leitura/gravação de um banco de dados tabular ou multidimensional.</span><span class="sxs-lookup"><span data-stu-id="b2d76-103">There are often situations when a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database administrator (dba) wants to change the read/write mode of a tabular or multidimensional database.</span></span> <span data-ttu-id="b2d76-104">Essas situações geralmente são orientadas pelas necessidades comerciais, como o compartilhamento do banco de dados entre um pool de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] servidores para uma melhor experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="b2d76-104">These situations are often driven by business needs, such as sharing the database among a pool of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] servers for a better user experience.</span></span>  
  
 <span data-ttu-id="b2d76-105">Um modo de banco de dados pode ser alternado de várias formas.</span><span class="sxs-lookup"><span data-stu-id="b2d76-105">A database mode can be switched in many ways.</span></span> <span data-ttu-id="b2d76-106">Este documento explica os cenários comuns a seguir:</span><span class="sxs-lookup"><span data-stu-id="b2d76-106">This document explains the following common scenarios:</span></span>  
  
-   <span data-ttu-id="b2d76-107">Usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2d76-107">Interactively using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span></span>  
  
-   <span data-ttu-id="b2d76-108">Usando o AMO de maneira programática</span><span class="sxs-lookup"><span data-stu-id="b2d76-108">Programmatically using AMO</span></span>  
  
-   <span data-ttu-id="b2d76-109">Por script usando XMLA</span><span class="sxs-lookup"><span data-stu-id="b2d76-109">By script using XMLA</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="b2d76-110">Procedimentos</span><span class="sxs-lookup"><span data-stu-id="b2d76-110">Procedures</span></span>  
  
#### <a name="to-switch-the-readwrite-mode-of-a-database-interactively-using-management-studio"></a><span data-ttu-id="b2d76-111">Para alternar o modo leitura/gravação de um banco de dados de maneira interativa usando o Management Studio</span><span class="sxs-lookup"><span data-stu-id="b2d76-111">To switch the read/write mode of a database interactively using Management Studio</span></span>  
  
1.  <span data-ttu-id="b2d76-112">Localize o banco de dados a ser alternado no painel esquerdo ou direito do [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2d76-112">Locate the database to be switched in the left or right pane of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="b2d76-113">Clique com o botão direito do mouse no banco de dados e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b2d76-113">Right-click the database and select **Properties**.</span></span> <span data-ttu-id="b2d76-114">Localize a pasta do banco de dados e anote o local.</span><span class="sxs-lookup"><span data-stu-id="b2d76-114">Find the database folder and note the location.</span></span> <span data-ttu-id="b2d76-115">Um local de armazenamento de banco de dados vazio indica que a pasta de banco de dados está localizada na pasta de dados do servidor.</span><span class="sxs-lookup"><span data-stu-id="b2d76-115">An empty database storage location indicates that the database folder is located in the server data folder.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b2d76-116">Assim que o banco de dados for desanexado, o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] já não pode lhe ajudar a obter o local do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b2d76-116">As soon as the database is detached, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] can no longer help you obtain the database location.</span></span>  
  
3.  <span data-ttu-id="b2d76-117">Clique com o botão direito do mouse no banco de dados e selecione **desanexar...**</span><span class="sxs-lookup"><span data-stu-id="b2d76-117">Right-click the database and select **Detach...**</span></span>  
  
4.  <span data-ttu-id="b2d76-118">Atribua uma senha ao banco de dados a ser desanexado e clique em **OK** para executar o comando Desanexar.</span><span class="sxs-lookup"><span data-stu-id="b2d76-118">Assign a password to the database to be detached, and then click **OK** to execute the detach command.</span></span>  
  
5.  <span data-ttu-id="b2d76-119">Localize a pasta **bancos de dados** no painel esquerdo ou direito de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b2d76-119">Locate the **Databases** folder in the left or right pane of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
6.  <span data-ttu-id="b2d76-120">Clique com o botão direito do mouse na pasta **bancos de dados** e selecione **anexar..** .</span><span class="sxs-lookup"><span data-stu-id="b2d76-120">Right-click the **Databases** folder and select **Attach...**</span></span>  
  
7.  <span data-ttu-id="b2d76-121">Na caixa de texto **pasta** , digite o local original da pasta do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b2d76-121">In the **folder** text box, type the original location of the database folder.</span></span> <span data-ttu-id="b2d76-122">Como alternativa, você pode usar o botão procurar (**...**) para localizar a pasta do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b2d76-122">Alternatively, you can use the browse button (**...**) to locate the database folder.</span></span>  
  
8.  <span data-ttu-id="b2d76-123">Selecione o modo leitura/gravação do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b2d76-123">Select the read/write mode for the database.</span></span>  
  
9. <span data-ttu-id="b2d76-124">Digite a senha que foi usada na etapa 3 e clique em **OK** para executar o comando attach.</span><span class="sxs-lookup"><span data-stu-id="b2d76-124">Type the password that was used in step 3 and click **OK** to execute the attach command.</span></span>  
  
#### <a name="to-switch-the-readwrite-mode-to-a-database-programmatically-using-amo"></a><span data-ttu-id="b2d76-125">Para alternar o modo leitura/gravação em um banco de dados usando o AMO de maneira programática</span><span class="sxs-lookup"><span data-stu-id="b2d76-125">To switch the read/write mode to a database programmatically using AMO</span></span>  
  
1.  <span data-ttu-id="b2d76-126">Em seu aplicativo C#, adapte o seguinte código de amostra e conclua as tarefas indicadas.</span><span class="sxs-lookup"><span data-stu-id="b2d76-126">In your C# application, adapt the following sample code and complete the indicated tasks.</span></span>  
  
 `private void SwitchReadWrite(Server server, string dbName,`  
  
 `ReadWriteMode dbReadWriteMode)`  
  
 `{`  
  
 `if (server.Databases.ContainsName(dbName))`  
  
 `{`  
  
 `Database db;`  
  
 `string databaseLocation;`  
  
 `db = server.Databases[dbName];`  
  
 `databaseLocation = db.DbStorageLocation;`  
  
 `if (databaseLocation == null)`  
  
 `{`  
  
 `string dataDir = server.ServerProperties["DataDir"].Value;`  
  
 `String[] possibleFolders = Directory.GetDirectories(dataDir, string.Concat(dbName,"*"), SearchOption.TopDirectoryOnly);`  
  
 `if (possibleFolders.Length > 1)`  
  
 `{`  
  
 `List<String> sortedFolders = new List<string>(possibleFolders.Length);`  
  
 `sortedFolders.AddRange(possibleFolders);`  
  
 `sortedFolders.Sort();`  
  
 `databaseLocation = sortedFolders[sortedFolders.Count - 1];`  
  
 `}`  
  
 `else`  
  
 `{`  
  
 `databaseLocation = possibleFolders[0];`  
  
 `}`  
  
 `}`  
  
 `db.Detach();`  
  
 `server.Attach(databaseLocation, dbReadWriteMode);`  
  
 `}`  
  
 `}`  
  
1.  <span data-ttu-id="b2d76-127">Em seu aplicativo C#, chame `SwitchReadWrite()` com os parâmetros necessários.</span><span class="sxs-lookup"><span data-stu-id="b2d76-127">In your C# application, invoke `SwitchReadWrite()` with the necessary parameters.</span></span>  
  
2.  <span data-ttu-id="b2d76-128">Compile e execute seu código para mover o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b2d76-128">Compile and execute your code to move the database.</span></span>  
  
#### <a name="to-switch-the-readwrite-mode-to-a-database-by-script-using-xmla"></a><span data-ttu-id="b2d76-129">Para alternar o modo leitura/gravação para um banco de dados por script usando XMLA</span><span class="sxs-lookup"><span data-stu-id="b2d76-129">To switch the read/write mode to a database by script using XMLA</span></span>  
  
1.  <span data-ttu-id="b2d76-130">Localize o banco de dados a ser alternado no painel esquerdo ou direito do [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2d76-130">Locate the database to be switched in the left or right pane of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="b2d76-131">Clique com o botão direito do mouse no banco de dados e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b2d76-131">Right-click the database and select **Properties**.</span></span> <span data-ttu-id="b2d76-132">Localize a pasta do banco de dados e anote o local.</span><span class="sxs-lookup"><span data-stu-id="b2d76-132">Find the database folder and note the location.</span></span> <span data-ttu-id="b2d76-133">Um local de armazenamento de banco de dados vazio indica que a pasta de banco de dados está localizada na pasta de dados do servidor.</span><span class="sxs-lookup"><span data-stu-id="b2d76-133">An empty database storage location indicates that the database folder is located in the server data folder.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b2d76-134">Assim que o banco de dados for desanexado, o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] já não pode lhe ajudar a obter o local do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b2d76-134">As soon as the database is detached, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] can no longer help you obtain the database location.</span></span>  
  
3.  <span data-ttu-id="b2d76-135">Abra uma nova guia XMLA em [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2d76-135">Open a new XMLA tab in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
4.  <span data-ttu-id="b2d76-136">Copie o modelo de script a seguir para XMLA:</span><span class="sxs-lookup"><span data-stu-id="b2d76-136">Copy the following script template for XMLA:</span></span>  
  
 `<Detach xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">`  
  
 `<Object>`  
  
 `<DatabaseID>%dbName%</DatabaseID>`  
  
 `<Password>%password%</Password>`  
  
 `</Object>`  
  
 `</Detach>`  
  
1.  <span data-ttu-id="b2d76-137">Substitua `%dbName%` pelo nome do banco de dados e `%password%` pela senha.</span><span class="sxs-lookup"><span data-stu-id="b2d76-137">Replace `%dbName%` with the name of the database and `%password%` with the password.</span></span> <span data-ttu-id="b2d76-138">Os caracteres % fazem parte do modelo e devem ser removidos.</span><span class="sxs-lookup"><span data-stu-id="b2d76-138">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="b2d76-139">Execute o comando XMLA.</span><span class="sxs-lookup"><span data-stu-id="b2d76-139">Execute the XMLA command.</span></span>  
  
3.  <span data-ttu-id="b2d76-140">Copiar o modelo de script a seguir para XMLA em uma nova guia XMLA</span><span class="sxs-lookup"><span data-stu-id="b2d76-140">Copy the following script template for XMLA in a new XMLA tab</span></span>  
  
 <span data-ttu-id="b2d76-141">`<Attach xmlns="https://schemas.microsoft.com/analysisservices/2003` `/engine` `">`</span><span class="sxs-lookup"><span data-stu-id="b2d76-141">`<Attach xmlns="https://schemas.microsoft.com/analysisservices/2003` `/engine` `">`</span></span>  
  
 `<Folder>%dbFolder%</Folder>`  
  
 `<ReadWriteMode xmlns="https://schemas.microsoft.com/analysisservices/2008/engine/100">%ReadOnlyMode%</ReadWriteMode>`  
  
 `</Attach>`  
  
1.  <span data-ttu-id="b2d76-142">Substitua `%dbFolder%` pelo caminho UNC completo da pasta do banco de dados, `%ReadOnlyMode%` pelo valor correspondente `ReadOnly` ou `ReadWrite` e `%password%` pela senha.</span><span class="sxs-lookup"><span data-stu-id="b2d76-142">Replace `%dbFolder%` with the complete UNC path of the database folder, `%ReadOnlyMode%` with the corresponding value `ReadOnly` or `ReadWrite`, and `%password%` with the password.</span></span> <span data-ttu-id="b2d76-143">Os caracteres % fazem parte do modelo e devem ser removidos.</span><span class="sxs-lookup"><span data-stu-id="b2d76-143">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="b2d76-144">Execute o comando XMLA.</span><span class="sxs-lookup"><span data-stu-id="b2d76-144">Execute the XMLA command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2d76-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b2d76-145">See Also</span></span>  
 <xref:Microsoft.AnalysisServices.Server.Attach%2A>   
 <span data-ttu-id="b2d76-146">[Microsoft. AnalysisServices. Database. Detach \*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span><span class="sxs-lookup"><span data-stu-id="b2d76-146">[Microsoft.AnalysisServices.Database.Detach\*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span></span>  
 <span data-ttu-id="b2d76-147">[Anexar e desanexar bancos de dados Analysis Services](attach-and-detach-analysis-services-databases.md) </span><span class="sxs-lookup"><span data-stu-id="b2d76-147">[Attach and Detach Analysis Services Databases](attach-and-detach-analysis-services-databases.md) </span></span>  
 <span data-ttu-id="b2d76-148">[Local de armazenamento do banco de dados](database-storage-location.md) </span><span class="sxs-lookup"><span data-stu-id="b2d76-148">[Database Storage Location](database-storage-location.md) </span></span>  
 <span data-ttu-id="b2d76-149">[ReadWriteModes do banco de dados](database-readwritemodes.md) </span><span class="sxs-lookup"><span data-stu-id="b2d76-149">[Database ReadWriteModes](database-readwritemodes.md) </span></span>  
 <span data-ttu-id="b2d76-150">[Anexar elemento](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span><span class="sxs-lookup"><span data-stu-id="b2d76-150">[Attach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span></span>  
 <span data-ttu-id="b2d76-151">[Elemento Detach](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span><span class="sxs-lookup"><span data-stu-id="b2d76-151">[Detach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span></span>  
 <span data-ttu-id="b2d76-152">[Elemento ReadWritemode](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span><span class="sxs-lookup"><span data-stu-id="b2d76-152">[ReadWriteMode Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span></span>  
 [<span data-ttu-id="b2d76-153">Elemento DbStorageLocation</span><span class="sxs-lookup"><span data-stu-id="b2d76-153">DbStorageLocation Element</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/dbstoragelocation-element)  
  
  
