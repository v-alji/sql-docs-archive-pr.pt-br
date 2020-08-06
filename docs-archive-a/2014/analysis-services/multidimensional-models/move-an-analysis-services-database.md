---
title: Mover um banco de dados Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- moving databases [Anlysis Services]
- moving databases
- operations [Analysis Services - multidimensional data]
ms.assetid: fa644e5d-e276-445e-98d9-673afcfb83fe
author: minewiskan
ms.author: owend
ms.openlocfilehash: bd9b099ad6765d9caccb9b0af6622eb4aa77d38c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684937"
---
# <a name="move-an-analysis-services-database"></a><span data-ttu-id="f6856-102">Mover um Banco de Dados do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="f6856-102">Move an Analysis Services Database</span></span>
  <span data-ttu-id="f6856-103">Frequentemente, há situações em que um dba (administrador de banco de dados) [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] quer mover um modelo de banco de dados multidimensional ou de tabela para um local diferente.</span><span class="sxs-lookup"><span data-stu-id="f6856-103">There are often situations when an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database administrator (dba) wants to move a multidimensional or tabular model database to a different location.</span></span> <span data-ttu-id="f6856-104">Essas situações frequentemente são conduzidas pelas necessidades comerciais, como a movimentação do banco de dados para um disco diferente em busca de um melhor desempenho, a obtenção de espaço para o crescimento do banco de dados ou para a atualização de um produto.</span><span class="sxs-lookup"><span data-stu-id="f6856-104">These situations are often driven by business needs, such as moving the database to a different disk for better performance, gaining room for database growth, or to upgrade a product.</span></span>  
  
 <span data-ttu-id="f6856-105">Um banco de dados pode ser movido de muitas formas.</span><span class="sxs-lookup"><span data-stu-id="f6856-105">A database can be moved in many ways.</span></span> <span data-ttu-id="f6856-106">Este documento explica os cenários comuns a seguir:</span><span class="sxs-lookup"><span data-stu-id="f6856-106">This document explains the following common scenarios:</span></span>  
  
-   <span data-ttu-id="f6856-107">Usando o SSMS de modo interativo</span><span class="sxs-lookup"><span data-stu-id="f6856-107">Interactively using SSMS</span></span>  
  
-   <span data-ttu-id="f6856-108">Usando o AMO de maneira programática</span><span class="sxs-lookup"><span data-stu-id="f6856-108">Programmatically using AMO</span></span>  
  
-   <span data-ttu-id="f6856-109">Por script usando XMLA</span><span class="sxs-lookup"><span data-stu-id="f6856-109">By script using XMLA</span></span>  
  
 <span data-ttu-id="f6856-110">Todos os cenários exigem que o usuário acesse a pasta do banco de dados e use um método para mover os arquivos para o destino final desejado.</span><span class="sxs-lookup"><span data-stu-id="f6856-110">All scenarios require the user to access the database folder and to use a method for moving the files to the desired final destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f6856-111">Desanexar um banco de dados sem atribuir uma senha a ele deixa o banco de dados em um estado não seguro.</span><span class="sxs-lookup"><span data-stu-id="f6856-111">Detaching a database without assigning a password to it leaves the database in an unsecured state.</span></span> <span data-ttu-id="f6856-112">Recomendamos atribuir uma senha ao banco de dados para proteger informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="f6856-112">We recommend assigning a password to the database to protect confidential information.</span></span> <span data-ttu-id="f6856-113">Além disso, a segurança de acesso correspondente deve ser aplicada à pasta do banco de dados, subpastas e arquivos para impedir o acesso não autorizado a ele.</span><span class="sxs-lookup"><span data-stu-id="f6856-113">Also, the corresponding access security should be applied to the database folder, sub-folders, and files to prevent unauthorized access to them.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="f6856-114">Procedimentos</span><span class="sxs-lookup"><span data-stu-id="f6856-114">Procedures</span></span>  
  
#### <a name="moving-a-database-interactively-using-ssms"></a><span data-ttu-id="f6856-115">Movendo um banco de dados de maneira interativa usando SSMS</span><span class="sxs-lookup"><span data-stu-id="f6856-115">Moving a database interactively using SSMS</span></span>  
  
1.  <span data-ttu-id="f6856-116">Localize o banco de dados a ser movido no painel esquerdo ou direito do SSMS.</span><span class="sxs-lookup"><span data-stu-id="f6856-116">Locate the database to be moved in the left or right pane of SSMS.</span></span>  
  
2.  <span data-ttu-id="f6856-117">Clique com o botão direito do mouse no banco de dados e selecione **desanexar...**</span><span class="sxs-lookup"><span data-stu-id="f6856-117">Right-click on the database and select **Detach...**</span></span>  
  
3.  <span data-ttu-id="f6856-118">Atribua uma senha ao banco de dados a ser desanexado e clique em **OK** para executar o comando detach.</span><span class="sxs-lookup"><span data-stu-id="f6856-118">Assign a password to the database to be detached, then click **OK** to execute the detach command.</span></span>  
  
4.  <span data-ttu-id="f6856-119">Use qualquer mecanismo de sistema operacional ou método padrão para mover arquivos para mover a pasta do banco de dados para o novo local.</span><span class="sxs-lookup"><span data-stu-id="f6856-119">Use any operating system mechanism or your standard method for moving files to move the database folder to the new location.</span></span>  
  
5.  <span data-ttu-id="f6856-120">Localize a pasta **Bancos de Dados** no painel esquerdo ou direito do SSMS.</span><span class="sxs-lookup"><span data-stu-id="f6856-120">Locate the **Databases** folder in the left or right pane of SSMS.</span></span>  
  
6.  <span data-ttu-id="f6856-121">Clique com o botão direito do mouse na pasta **bancos de dados** e selecione **anexar..** .</span><span class="sxs-lookup"><span data-stu-id="f6856-121">Right-click on the **Databases** folder and select **Attach...**</span></span>  
  
7.  <span data-ttu-id="f6856-122">Na caixa de texto **pasta** , digite o novo local da pasta do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f6856-122">In the **folder** text box, type the new location of the database folder.</span></span> <span data-ttu-id="f6856-123">Como alternativa, você pode usar o botão procurar (**...**) para localizar a pasta do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f6856-123">Alternatively, you can use the browse button (**...**) to locate the database folder.</span></span>  
  
8.  <span data-ttu-id="f6856-124">Selecione o `ReadWrite` modo do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f6856-124">Select the `ReadWrite` mode for the database.</span></span>  
  
9. <span data-ttu-id="f6856-125">Digite a senha usada na etapa 3 e clique em **OK** para executar o comando Anexar.</span><span class="sxs-lookup"><span data-stu-id="f6856-125">Type the password used in step 3 and click **OK** to execute the attach command.</span></span>  
  
#### <a name="moving-a-database-programmatically-using-amo"></a><span data-ttu-id="f6856-126">Movendo um banco de dados que usa AMO programaticamente</span><span class="sxs-lookup"><span data-stu-id="f6856-126">Moving a database programmatically using AMO</span></span>  
  
1.  <span data-ttu-id="f6856-127">Em seu aplicativo C#, adapte o seguinte código de amostra e conclua as tarefas indicadas.</span><span class="sxs-lookup"><span data-stu-id="f6856-127">In your C# application, adapt the following sample code and complete the indicated tasks.</span></span>  
  
 `private void MoveDb(Server server, string dbName,`  
  
 `string dbInitialLocation, string dbFinalLocation,`  
  
 `string dbPassword, ReadWriteMode dbReadWriteMode)`  
  
 `{`  
  
 `//Verify dbInitialLocation exists before continuing`  
  
 `if (server.Databases.ContainsName(dbName))`  
  
 `{`  
  
 `Database db;`  
  
 `//Save current cursor and change cursor to Cursors.WaitCursor`  
  
 `db = server.Databases[dbName];`  
  
 `db.Detach(dbPassword);`  
  
 `//Add your own code to copy the database files to the destination where you intend to attach the database`  
  
 `//Verify dbFinalLocation exists before continuing`  
  
 `server.Attach(dbFinalLocation, dbReadWriteMode, dbPassword);`  
  
 `//Restore cursor to its original`  
  
 `}`  
  
 `}`  
  
1.  <span data-ttu-id="f6856-128">Em seu aplicativo C#, chame `MoveDb()` com os parâmetros necessários.</span><span class="sxs-lookup"><span data-stu-id="f6856-128">In your C# application, invoke `MoveDb()` with the necessary parameters.</span></span>  
  
2.  <span data-ttu-id="f6856-129">Compile e execute seu código para mover o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f6856-129">Compile and execute your code to move the database.</span></span>  
  
#### <a name="moving-a-database-by-script-using-xmla"></a><span data-ttu-id="f6856-130">Movendo um banco de dados por script usando XMLA</span><span class="sxs-lookup"><span data-stu-id="f6856-130">Moving a database by script using XMLA</span></span>  
  
1.  <span data-ttu-id="f6856-131">Abra uma nova guia XMLA no SSMS.</span><span class="sxs-lookup"><span data-stu-id="f6856-131">Open a new XMLA tab in SSMS.</span></span>  
  
2.  <span data-ttu-id="f6856-132">Copie o modelo de script a seguir para XMLA</span><span class="sxs-lookup"><span data-stu-id="f6856-132">Copy the following script template for XMLA</span></span>  
  
 `<Detach xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">`  
  
 `<Object>`  
  
 `<DatabaseID>%dbName%</DatabaseID>`  
  
 `<Password>%password%</Password>`  
  
 `</Object>`  
  
 `</Detach>`  
  
1.  <span data-ttu-id="f6856-133">Substitua `%dbName%` pelo nome do banco de dados e `%password%` pela senha.</span><span class="sxs-lookup"><span data-stu-id="f6856-133">Replace `%dbName%` with the name of the database and `%password%` with the password.</span></span> <span data-ttu-id="f6856-134">Os caracteres % fazem parte do modelo e devem ser removidos.</span><span class="sxs-lookup"><span data-stu-id="f6856-134">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="f6856-135">Execute o comando XMLA.</span><span class="sxs-lookup"><span data-stu-id="f6856-135">Execute the XMLA command.</span></span>  
  
3.  <span data-ttu-id="f6856-136">Use qualquer mecanismo de sistema operacional ou método padrão para mover arquivos para mover a pasta do banco de dados para o novo local.</span><span class="sxs-lookup"><span data-stu-id="f6856-136">Use any operating system mechanism or your standard method for moving files to move the database folder to the new location.</span></span>  
  
4.  <span data-ttu-id="f6856-137">Copiar o modelo de script a seguir para XMLA em uma nova guia XMLA</span><span class="sxs-lookup"><span data-stu-id="f6856-137">Copy the following script template for XMLA in a new XMLA tab</span></span>  
  
 `<Attach xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">`  
  
 `<Folder>%dbFolder%</Folder>`  
  
 `<ReadWriteMode xmlns="https://schemas.microsoft.com/analysisservices/2008/engine/100">%ReadOnlyMode%</ReadWriteMode>`  
  
 `</Attach>`  
  
1.  <span data-ttu-id="f6856-138">Substitua `%dbFolder%` pelo caminho UNC completo da pasta do banco de dados, `%ReadOnlyMode%` pelo valor correspondente `ReadOnly` ou `ReadWrite` e `%password%` pela senha.</span><span class="sxs-lookup"><span data-stu-id="f6856-138">Replace `%dbFolder%` with the complete UNC path of the database folder, `%ReadOnlyMode%` with the corresponding value `ReadOnly` or `ReadWrite`, and `%password%` with the password.</span></span> <span data-ttu-id="f6856-139">Os caracteres % fazem parte do modelo e devem ser removidos.</span><span class="sxs-lookup"><span data-stu-id="f6856-139">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="f6856-140">Execute o comando XMLA.</span><span class="sxs-lookup"><span data-stu-id="f6856-140">Execute the XMLA command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6856-141">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f6856-141">See Also</span></span>  
 <xref:Microsoft.AnalysisServices.Server.Attach%2A>   
 <span data-ttu-id="f6856-142">[Microsoft. AnalysisServices. Database. Detach \*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span><span class="sxs-lookup"><span data-stu-id="f6856-142">[Microsoft.AnalysisServices.Database.Detach\*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span></span>  
 <span data-ttu-id="f6856-143">[Anexar e desanexar bancos de dados Analysis Services](attach-and-detach-analysis-services-databases.md) </span><span class="sxs-lookup"><span data-stu-id="f6856-143">[Attach and Detach Analysis Services Databases](attach-and-detach-analysis-services-databases.md) </span></span>  
 <span data-ttu-id="f6856-144">[Local de armazenamento do banco de dados](database-storage-location.md) </span><span class="sxs-lookup"><span data-stu-id="f6856-144">[Database Storage Location](database-storage-location.md) </span></span>  
 <span data-ttu-id="f6856-145">[ReadWriteModes do banco de dados](database-readwritemodes.md) </span><span class="sxs-lookup"><span data-stu-id="f6856-145">[Database ReadWriteModes](database-readwritemodes.md) </span></span>  
 <span data-ttu-id="f6856-146">[Anexar elemento](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span><span class="sxs-lookup"><span data-stu-id="f6856-146">[Attach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span></span>  
 <span data-ttu-id="f6856-147">[Elemento Detach](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span><span class="sxs-lookup"><span data-stu-id="f6856-147">[Detach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span></span>  
 <span data-ttu-id="f6856-148">[Elemento ReadWritemode](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span><span class="sxs-lookup"><span data-stu-id="f6856-148">[ReadWriteMode Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span></span>  
 [<span data-ttu-id="f6856-149">Elemento DbStorageLocation</span><span class="sxs-lookup"><span data-stu-id="f6856-149">DbStorageLocation Element</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/dbstoragelocation-element)  
  
  
