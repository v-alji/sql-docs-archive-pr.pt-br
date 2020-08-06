---
title: Propriedades do banco de dados (página Arquivos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.files.f1
ms.assetid: 3c030e51-db82-4b43-b1e5-8547ddd3de87
author: stevestein
ms.author: sstein
ms.openlocfilehash: 955a17857ce0d847fb712473dddd581a072ab83d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678786"
---
# <a name="database-properties-files-page"></a><span data-ttu-id="884ef-102">Propriedades do Banco de Dados (página Arquivos)</span><span class="sxs-lookup"><span data-stu-id="884ef-102">Database Properties (Files Page)</span></span>
  <span data-ttu-id="884ef-103">Use esta página para criar um novo banco de dados ou para exibir ou modificar as propriedades do banco de dados selecionado.</span><span class="sxs-lookup"><span data-stu-id="884ef-103">Use this page to create a new database, or view or modify properties for the selected database.</span></span> <span data-ttu-id="884ef-104">Este tópico se aplica às **Propriedades do Banco de Dados (página Arquivos)** de bancos de dados existentes e ao **Novo Banco de Dados (página Geral)** .</span><span class="sxs-lookup"><span data-stu-id="884ef-104">This topic applies to the **Database Properties (Files Page)** for existing databases, and to the **New Database (General Page)**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="884ef-105">Lista de elementos da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="884ef-105">UI element list</span></span>  
 <span data-ttu-id="884ef-106">**Nome do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="884ef-106">**Database name**</span></span>  
 <span data-ttu-id="884ef-107">Adicione ou exiba o nome do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="884ef-107">Add or display the name of the database.</span></span>  
  
 <span data-ttu-id="884ef-108">**Proprietário**</span><span class="sxs-lookup"><span data-stu-id="884ef-108">**Owner**</span></span>  
 <span data-ttu-id="884ef-109">Especifique o proprietário do banco de dados selecionando na lista.</span><span class="sxs-lookup"><span data-stu-id="884ef-109">Specify the owner of the database by selecting from the list.</span></span>  
  
 <span data-ttu-id="884ef-110">**Usar indexação de texto completo**</span><span class="sxs-lookup"><span data-stu-id="884ef-110">**Use full-text indexing**</span></span>  
 <span data-ttu-id="884ef-111">Essa caixa de seleção fica marcada e desabilitada porque a indexação de texto completo está sempre habilitada no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="884ef-111">This check box is checked and disabled because full-text indexing is always enabled in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="884ef-112">Para obter mais informações, consulte [Pesquisa de texto completo](../search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="884ef-112">For more information, see [Full-Text Search](../search/full-text-search.md).</span></span>  
  
 <span data-ttu-id="884ef-113">**Arquivos do banco de dados**</span><span class="sxs-lookup"><span data-stu-id="884ef-113">**Database Files**</span></span>  
 <span data-ttu-id="884ef-114">Adicione, exiba, modifique ou remova arquivos do banco de dados associado.</span><span class="sxs-lookup"><span data-stu-id="884ef-114">Add, view, modify, or remove database files for the associated database.</span></span> <span data-ttu-id="884ef-115">Arquivos de banco de dados têm as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="884ef-115">Database files have the following properties:</span></span>  
  
 <span data-ttu-id="884ef-116">**Nome Lógico**</span><span class="sxs-lookup"><span data-stu-id="884ef-116">**Logical Name**</span></span>  
 <span data-ttu-id="884ef-117">Digite ou modifique o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="884ef-117">Enter or modify the name of the file.</span></span>  
  
 <span data-ttu-id="884ef-118">**Tipo de arquivo**</span><span class="sxs-lookup"><span data-stu-id="884ef-118">**File Type**</span></span>  
 <span data-ttu-id="884ef-119">Selecione o tipo de arquivo na lista.</span><span class="sxs-lookup"><span data-stu-id="884ef-119">Select the file type from the list.</span></span> <span data-ttu-id="884ef-120">O tipo de arquivo pode ser **Dados**, **Log**ou **Dados de Filestream**.</span><span class="sxs-lookup"><span data-stu-id="884ef-120">The file type can be **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="884ef-121">Você não pode modificar o tipo de arquivo de um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="884ef-121">You cannot modify the file type of an existing file.</span></span>  
  
 <span data-ttu-id="884ef-122">Selecione **Dados do Fluxo de Arquivos** se estiver adicionando arquivos (contêineres) a um grupo de arquivos com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="884ef-122">Select **Filestream Data** if you are adding files (containers) to a memory-optimized filegroup.</span></span>  
  
 <span data-ttu-id="884ef-123">Para adicionar arquivos (contêineres) a um grupo de arquivos de dados de Filestream, o FILESTREAM deve estar habilitado.</span><span class="sxs-lookup"><span data-stu-id="884ef-123">To add files (containers) to a Filestream data filegroup, FILESTREAM must be enabled.</span></span> <span data-ttu-id="884ef-124">Você pode habilitar o FILESTREAM usando a caixa de diálogo [Propriedades do Servidor (página Avançado)](../../database-engine/configure-windows/server-properties-advanced-page.md) .</span><span class="sxs-lookup"><span data-stu-id="884ef-124">You can enable FILESTREAM by using the [Server Properties (Advanced Page)](../../database-engine/configure-windows/server-properties-advanced-page.md) dialog box.</span></span>  
  
 <span data-ttu-id="884ef-125">**Grupo de arquivos**</span><span class="sxs-lookup"><span data-stu-id="884ef-125">**Filegroup**</span></span>  
 <span data-ttu-id="884ef-126">Selecione o grupo de arquivos do arquivo na lista.</span><span class="sxs-lookup"><span data-stu-id="884ef-126">Select the filegroup for the file from the list.</span></span> <span data-ttu-id="884ef-127">Por padrão, o grupo de arquivos é PRIMARY.</span><span class="sxs-lookup"><span data-stu-id="884ef-127">By default, the filegroup is PRIMARY.</span></span> <span data-ttu-id="884ef-128">Você pode criar um grupo de arquivos selecionando **\<new filegroup>** e inserindo informações sobre ele na caixa de diálogo **Novo Grupo de Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="884ef-128">You can create a new filegroup by selecting **\<new filegroup>** and entering information about the filegroup in the **New Filegroup** dialog box.</span></span> <span data-ttu-id="884ef-129">Um novo grupo de arquivos também pode ser criado na página **Grupo de Arquivos** .</span><span class="sxs-lookup"><span data-stu-id="884ef-129">A new filegroup can also be created on the **Filegroup** page.</span></span> <span data-ttu-id="884ef-130">Você não pode modificar o grupo de arquivos de um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="884ef-130">You cannot modify the filegroup of an existing file.</span></span>  
  
 <span data-ttu-id="884ef-131">Ao adicionar arquivos (contêineres) a um grupo de arquivos com otimização de memória, o campo de **Grupo de Arquivos** será preenchido com o nome do grupo de arquivos com otimização de memória do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="884ef-131">When adding files (containers) to a memory-optimized filegroup, the **Filegroup** field will be populated with the name of the database's memory-optimized filegroup.</span></span>  
  
 <span data-ttu-id="884ef-132">**Tamanho Inicial**</span><span class="sxs-lookup"><span data-stu-id="884ef-132">**Initial Size**</span></span>  
 <span data-ttu-id="884ef-133">Digite ou modifique o tamanho inicial do arquivo em megabytes.</span><span class="sxs-lookup"><span data-stu-id="884ef-133">Enter or modify the initial size for the file in megabytes.</span></span> <span data-ttu-id="884ef-134">Por padrão, esse é o valor do banco de dados **modelo** .</span><span class="sxs-lookup"><span data-stu-id="884ef-134">By default, this is the value of the **model** database.</span></span>  
  
 <span data-ttu-id="884ef-135">Esse campo não é válido para arquivos de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="884ef-135">This field is not valid for FILESTREAM files.</span></span>  
  
 <span data-ttu-id="884ef-136">Para arquivos em grupos de arquivos com otimização de memória, este campo não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="884ef-136">For files in memory-optimized filegroups, this field cannot be modified.</span></span>  
  
 <span data-ttu-id="884ef-137">**Aumento Automático**</span><span class="sxs-lookup"><span data-stu-id="884ef-137">**Autogrowth**</span></span>  
 <span data-ttu-id="884ef-138">Selecione ou exiba as propriedades de aumento automático do arquivo.</span><span class="sxs-lookup"><span data-stu-id="884ef-138">Select or display the autogrowth properties for the file.</span></span> <span data-ttu-id="884ef-139">Essas propriedades controlam como o arquivo se expande quando seu tamanho máximo é alcançado.</span><span class="sxs-lookup"><span data-stu-id="884ef-139">These properties control how the file expands when its maximum file size is reached.</span></span> <span data-ttu-id="884ef-140">Para editar valores de aumento automático, clique no botão de edição ao lado das propriedades de aumento automático do arquivo desejado e altere os valores na caixa de diálogo **Alterar Aumento Automático** .</span><span class="sxs-lookup"><span data-stu-id="884ef-140">To edit autogrowth values, click the edit button next to the autogrowth properties for the file that you want, and change the values in the **Change Autogrowth** dialog box.</span></span> <span data-ttu-id="884ef-141">Por padrão, esses são os valores do banco de dados **modelo** .</span><span class="sxs-lookup"><span data-stu-id="884ef-141">By default, these are the values of the **model** database.</span></span>  
  
 <span data-ttu-id="884ef-142">Esse campo não é válido para arquivos de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="884ef-142">This field is not valid for FILESTREAM files.</span></span>  
  
 <span data-ttu-id="884ef-143">Para arquivos em grupos de arquivos com otimização de memória, este campo deve ser **Ilimitado**.</span><span class="sxs-lookup"><span data-stu-id="884ef-143">For files in memory-optimized filegroups, this field should be **Unlimited**.</span></span>  
  
 <span data-ttu-id="884ef-144">**Caminho**</span><span class="sxs-lookup"><span data-stu-id="884ef-144">**Path**</span></span>  
 <span data-ttu-id="884ef-145">Exibe o caminho do arquivo selecionado.</span><span class="sxs-lookup"><span data-stu-id="884ef-145">Displays the path of the selected file.</span></span> <span data-ttu-id="884ef-146">Para especificar um caminho para um novo arquivo, clique no botão de edição próximo ao caminho do arquivo e navegue até a pasta de destino.</span><span class="sxs-lookup"><span data-stu-id="884ef-146">To specify a path for a new file, click the edit button next to the path for the file, and navigate to the destination folder.</span></span> <span data-ttu-id="884ef-147">Você não pode modificar o caminho de um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="884ef-147">You cannot modify the path of an existing file.</span></span>  
  
 <span data-ttu-id="884ef-148">Para arquivos de FILESTREAM, o caminho é uma pasta.</span><span class="sxs-lookup"><span data-stu-id="884ef-148">For FILESTREAM files, the path is a folder.</span></span> <span data-ttu-id="884ef-149">O [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] criará os arquivos subjacentes nesta pasta.</span><span class="sxs-lookup"><span data-stu-id="884ef-149">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] will create the underlying files in this folder.</span></span>  
  
 <span data-ttu-id="884ef-150">**Nome do Arquivo**</span><span class="sxs-lookup"><span data-stu-id="884ef-150">**File Name**</span></span>  
 <span data-ttu-id="884ef-151">Exibe o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="884ef-151">Displays the name of the file.</span></span>  
  
 <span data-ttu-id="884ef-152">Este campo não é válido para arquivos de FILESTREAM, incluindo arquivos em grupos de arquivos com otimização de memória.</span><span class="sxs-lookup"><span data-stu-id="884ef-152">This field is not valid for FILESTREAM files, including files in memory-optimized filegroups.</span></span>  
  
 <span data-ttu-id="884ef-153">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="884ef-153">**Add**</span></span>  
 <span data-ttu-id="884ef-154">Adicione um novo arquivo ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="884ef-154">Add a new file to the database.</span></span>  
  
 <span data-ttu-id="884ef-155">**Remover**</span><span class="sxs-lookup"><span data-stu-id="884ef-155">**Remove**</span></span>  
 <span data-ttu-id="884ef-156">Exclua o arquivo selecionado do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="884ef-156">Delete the selected file from the database.</span></span> <span data-ttu-id="884ef-157">Um arquivo não pode ser removido, a menos que esteja vazio.</span><span class="sxs-lookup"><span data-stu-id="884ef-157">A file cannot be removed unless it is empty.</span></span> <span data-ttu-id="884ef-158">O arquivo de dados principal e o arquivo de log não podem ser removidos.</span><span class="sxs-lookup"><span data-stu-id="884ef-158">The primary data file and log file cannot be removed.</span></span>  
  
 <span data-ttu-id="884ef-159">Para obter informações sobre arquivos, consulte [Database Files and Filegroups](database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="884ef-159">For information about files, see [Database Files and Filegroups](database-files-and-filegroups.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="884ef-160">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="884ef-160">See Also</span></span>  
 <span data-ttu-id="884ef-161">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="884ef-161">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="884ef-162">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="884ef-162">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
