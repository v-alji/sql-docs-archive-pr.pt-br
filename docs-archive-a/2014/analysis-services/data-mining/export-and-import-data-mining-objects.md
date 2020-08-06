---
title: Exportar e importar objetos de mineração de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- backing up databases [Analysis Services]
- exporting mining models
- exporting mining structures
- mining structures [Analysis Services], creating
- mining structures [DMX], exporting
- mining models [Analysis Services], migration
ms.assetid: 10a83b13-2640-4ff5-80c8-a35e1d692908
author: minewiskan
ms.author: owend
ms.openlocfilehash: 01e8651dd7e9d59012b0ba065bccb9ea62a1ee54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576058"
---
# <a name="export-and-import-data-mining-objects"></a><span data-ttu-id="7de3e-102">Exportar e importar objetos de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="7de3e-102">Export and Import Data Mining Objects</span></span>
  <span data-ttu-id="7de3e-103">Além da funcionalidade fornecida no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para soluções de backup, restauração e migração, a Mineração de Dados do SQL Server fornece a capacidade de transferir rapidamente estruturas e modelos de mineração de dados entre servidores diferentes usando extensões DMX.</span><span class="sxs-lookup"><span data-stu-id="7de3e-103">In addition to the functionality provided in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] for backing up, restoring, and migrating solutions, SQL Server Data Mining provides the ability to quickly transfer data mining structures and models between different servers by using Data Mining Extensions (DMX).</span></span>  
  
 <span data-ttu-id="7de3e-104">Se a sua solução de mineração de dados usar dados relacionais, em vez de um banco de dados multidimensional, a transferência de modelos com o uso de `EXPORT` e `IMPORT` será muito mais rápida e fácil do que com o uso da restauração do banco de dados ou da implantação de uma solução inteira.</span><span class="sxs-lookup"><span data-stu-id="7de3e-104">If your data mining solution uses relational data instead of a multidimensional database, transferring models by using `EXPORT` and `IMPORT` is much faster and easier than either using database restore or deploying an entire solution.</span></span>  
  
 <span data-ttu-id="7de3e-105">Esta seção fornece uma visão geral de como transferir estruturas de mineração de dados e modelos usando instruções DMX.</span><span class="sxs-lookup"><span data-stu-id="7de3e-105">This section provides an overview of how to transfer data mining structures and models by using DMX statements.</span></span> <span data-ttu-id="7de3e-106">Para obter detalhes sobre a sintaxe, junto com exemplos, consulte [EXPORT &#40;DMX&#41;](/sql/dmx/export-dmx) e [IMPORT &#40;DMX&#41;](/sql/dmx/import-dmx).</span><span class="sxs-lookup"><span data-stu-id="7de3e-106">For details of the syntax, together with examples, see [EXPORT &#40;DMX&#41;](/sql/dmx/export-dmx) and [IMPORT &#40;DMX&#41;](/sql/dmx/import-dmx).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7de3e-107">Você deve ser um administrador de banco de dados ou servidor para exportar ou importar objetos de um banco de dados do Microsoft SQL Server Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="7de3e-107">You must be a database or server administrator to export or import objects from a Microsoft SQL Server Analysis Services database.</span></span>  
  
## <a name="exporting-data-mining-structures"></a><span data-ttu-id="7de3e-108">Exportando estruturas de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="7de3e-108">Exporting Data Mining Structures</span></span>  
 <span data-ttu-id="7de3e-109">Quando você exporta uma estrutura de mineração, a instrução EXPORT exporta todos os modelos associados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7de3e-109">When you export a mining structure, the EXPORT statement automatically exports all associated models.</span></span> <span data-ttu-id="7de3e-110">Se você quiser controlar os objetos que são exportados, especifique cada objeto pelo nome.</span><span class="sxs-lookup"><span data-stu-id="7de3e-110">If you want to control the objects that are exported, you must specify each object by name.</span></span>  
  
 <span data-ttu-id="7de3e-111">Se a estrutura de mineração tiver sido processada e os resultados armazenados em cache, o que é o comportamento padrão, quando você exportar a estrutura de mineração, a definição conterá um resumo dos dados nos quais a estrutura se baseia.</span><span class="sxs-lookup"><span data-stu-id="7de3e-111">If the mining structure has been processed and the results have been cached, which is the default behavior, when you export the mining structure, the definition contains a summary of the data on which the structure is based.</span></span> <span data-ttu-id="7de3e-112">Para remover esse resumo, você deve limpar o cache associado com a estrutura de mineração executando uma operação `Process Clear Structure`.</span><span class="sxs-lookup"><span data-stu-id="7de3e-112">To remove this summary, you must clear the cache associated with the mining structure by performing a `Process Clear Structure` operation.</span></span> <span data-ttu-id="7de3e-113">Para obter mais informações, consulte [Processar uma estrutura de mineração](process-a-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="7de3e-113">For more information, see [Process a Mining Structure](process-a-mining-structure.md).</span></span>  
  
### <a name="exporting-data-mining-models"></a><span data-ttu-id="7de3e-114">Exportando modelos de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="7de3e-114">Exporting Data Mining Models</span></span>  
 <span data-ttu-id="7de3e-115">Você pode usar a palavra-chave `WITH DEPENDENCIES` para exportar a fonte de dados e a definição de exibição da fonte de dados junto com o modelo de mineração e sua estrutura.</span><span class="sxs-lookup"><span data-stu-id="7de3e-115">You can use the `WITH DEPENDENCIES` keyword to export the data source and data source view definition together with the mining model and its structure.</span></span>  
  
 <span data-ttu-id="7de3e-116">Quando você exportar um modelo de mineração sem exportar dependências, a instrução EXPORT exportará a definição do modelo de mineração e sua estrutura de mineração, mas não a definição das fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="7de3e-116">When you export a mining model without exporting its dependencies, the EXPORT statement will export the definition of the mining model and its mining structure, but does not export the definition of the data sources.</span></span> <span data-ttu-id="7de3e-117">Em virtude disso, após a importação do modelo, você poderá percorrê-lo imediatamente, mas se quiser reprocessar o modelo de mineração no servidor de destino ou executar consultas nos dados subjacentes, será necessário criar uma fonte de dados correspondente no servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="7de3e-117">As a consequence, after you import the model you will be able to browse the model immediately, but if you want to reprocess the mining model on the target server, or run queries against the underlying data, you must create a corresponding data source on the destination server.</span></span>  
  
## <a name="importing-data-mining-structures-and-models"></a><span data-ttu-id="7de3e-118">Importando estruturas e modelos de mineração de dados</span><span class="sxs-lookup"><span data-stu-id="7de3e-118">Importing Data Mining Structures and Models</span></span>  
 <span data-ttu-id="7de3e-119">Quando um objeto de mineração de dados é importado, esse objeto é importado para o servidor e o banco de dados em que você está conectado durante a execução da instrução IMPORT.</span><span class="sxs-lookup"><span data-stu-id="7de3e-119">When you import a data mining object, the object is imported to the server and database to which you are connected when you execute the IMPORT statement.</span></span> <span data-ttu-id="7de3e-120">Se o arquivo de importação incluir um banco de dados não existente no servidor, o banco de dados será criado.</span><span class="sxs-lookup"><span data-stu-id="7de3e-120">If the import file includes a database that does not exist on the server, the database will be created.</span></span>  
  
 <span data-ttu-id="7de3e-121">Você também pode importar uma estrutura de mineração ou modelo de mineração usando o comando `Restore`.</span><span class="sxs-lookup"><span data-stu-id="7de3e-121">You can also import a mining structure or mining model by using the `Restore` command.</span></span> <span data-ttu-id="7de3e-122">As estruturas ou os modelos serão restaurados no banco de dados que tem o mesmo nome do banco de dados do qual foram exportados.</span><span class="sxs-lookup"><span data-stu-id="7de3e-122">Your models or structures will be restored into the database that has the same name as the database from which they were exported.</span></span> <span data-ttu-id="7de3e-123">Para obter mais informações, consulte [Opções de restauração](../multidimensional-models/restore-options.md).</span><span class="sxs-lookup"><span data-stu-id="7de3e-123">For more information, see [Restore Options](../multidimensional-models/restore-options.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7de3e-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="7de3e-124">Remarks</span></span>  
 <span data-ttu-id="7de3e-125">Você não poderá importar uma estrutura ou modelo para um servidor se já houver um desses itens com o mesmo nome no servidor.</span><span class="sxs-lookup"><span data-stu-id="7de3e-125">You cannot import a model or structure to a server if a model or structure of the same name already exists on that server.</span></span> <span data-ttu-id="7de3e-126">Além disso, não é possível exportar um objeto de mineração de dados e depois modificar seu nome no arquivo de exportação.</span><span class="sxs-lookup"><span data-stu-id="7de3e-126">Also, you cannot export a data mining object and then modify the name of that object in the export file.</span></span> <span data-ttu-id="7de3e-127">Assim, se você antecipar conflitos de nome, exclua o objeto de mineração de dados no servidor de destino ou renomeie esse objeto antes de exportar a definição.</span><span class="sxs-lookup"><span data-stu-id="7de3e-127">Therefore, if you anticipate naming conflicts, you should either delete the data mining object on the target server, or rename the data mining object before you export the definition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7de3e-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7de3e-128">See Also</span></span>  
 [<span data-ttu-id="7de3e-129">Gerenciamento de soluções de mineração de dados e objetos</span><span class="sxs-lookup"><span data-stu-id="7de3e-129">Management of Data Mining Solutions and Objects</span></span>](management-of-data-mining-solutions-and-objects.md)  
  
  
