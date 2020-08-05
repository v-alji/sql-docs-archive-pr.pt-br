---
title: Gerenciador de Conexões do Cache | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Cache connection manager
ms.assetid: bdc92038-3720-4795-8a5c-79b963f2c952
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b8a7cc8bbe9e93c385fca6257e0be2e79bd3148a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574219"
---
# <a name="cache-connection-manager"></a><span data-ttu-id="b4764-102">Gerenciador de conexões do cache</span><span class="sxs-lookup"><span data-stu-id="b4764-102">Cache Connection Manager</span></span>
  <span data-ttu-id="b4764-103">O gerenciador de conexões do Cache lê dados da transformação Cache ou de um arquivo de cache (.caw) e salva os dados em um arquivo de cache.</span><span class="sxs-lookup"><span data-stu-id="b4764-103">The Cache connection manager reads data from the Cache transform or from a cache file (.caw), and can save the data to a cache file.</span></span> <span data-ttu-id="b4764-104">Se você configurar o gerenciador de conexões do Cache para usar um arquivo de cache, os dados sempre serão armazenados na memória.</span><span class="sxs-lookup"><span data-stu-id="b4764-104">Whether you configure the Cache connection manager to use a cache file, the data is always stored in memory.</span></span>  
  
 <span data-ttu-id="b4764-105">A transformação Cache grava dados de uma fonte de dados conectada no fluxo de dados para um gerenciador de conexões do Cache.</span><span class="sxs-lookup"><span data-stu-id="b4764-105">The Cache Transform transformation writes data from a connected data source in the data flow to a Cache connection manager.</span></span> <span data-ttu-id="b4764-106">A transformação Pesquisa em um pacote realiza pesquisas nos dados.</span><span class="sxs-lookup"><span data-stu-id="b4764-106">The Lookup transformation in a package performs lookups on the data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4764-107">O gerenciador de conexões do Cache não oferece suporte aos tipos de dados BLOB (objetos binários grandes) DT_TEXT, DT_NTEXT e DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="b4764-107">The Cache connection manager does not support the Binary Large Object (BLOB) data types DT_TEXT, DT_NTEXT, and DT_IMAGE.</span></span> <span data-ttu-id="b4764-108">Se o conjunto de dados de referência contiver um tipo de dados BLOB, o componente irá falhar quando o pacote for executado.</span><span class="sxs-lookup"><span data-stu-id="b4764-108">If the reference dataset contains a BLOB data type, the component will fail when you run the package.</span></span> <span data-ttu-id="b4764-109">Você pode usar o **Editor do Gerenciador de Conexões de Cache** para modificar os tipos de dados da coluna.</span><span class="sxs-lookup"><span data-stu-id="b4764-109">You can use the **Cache Connection Manager Editor** to modify column data types.</span></span> <span data-ttu-id="b4764-110">Para obter mais informações, consulte [Cache Connection Manager Editor](../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="b4764-110">For more information, see [Cache Connection Manager Editor](../cache-connection-manager-editor.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4764-111">O nível de proteção do pacote não se aplica ao arquivo de cache.</span><span class="sxs-lookup"><span data-stu-id="b4764-111">The protection level of the package does not apply to the cache file.</span></span> <span data-ttu-id="b4764-112">Se o arquivo de cache tiver informações confidenciais, use uma lista de controle de acesso (ACL) para restringir o acesso ao local ou à pasta na qual você deseja armazenar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="b4764-112">If the cache file contains sensitive information, use an access control list (ACL) to restrict access to the location or folder in which you store the file.</span></span> <span data-ttu-id="b4764-113">Você deve habilitar o acesso apenas para determinadas contas.</span><span class="sxs-lookup"><span data-stu-id="b4764-113">You should enable access only to certain accounts.</span></span> <span data-ttu-id="b4764-114">Para obter mais informações, consulte [Acesso aos arquivos usados por pacotes](../access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="b4764-114">For more information, see [Access to Files Used by Packages](../access-to-files-used-by-packages.md).</span></span>  
  
## <a name="configuration-of-the-cache-connection-manager"></a><span data-ttu-id="b4764-115">Configuração do gerenciador de conexões do Cache</span><span class="sxs-lookup"><span data-stu-id="b4764-115">Configuration of the Cache Connection Manager</span></span>  
 <span data-ttu-id="b4764-116">Você pode configurar o gerenciador de conexões do Cache das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="b4764-116">You can configure the Cache connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="b4764-117">Indique se precisa usar um arquivo de cache.</span><span class="sxs-lookup"><span data-stu-id="b4764-117">Indicate whether to use a cache file.</span></span>  
  
     <span data-ttu-id="b4764-118">Se você configurar o gerenciador de conexões de cache para usar um arquivo de cache, o gerenciador irá realizar uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="b4764-118">If you configure the cache connection manager to use a cache file, the connection manager will do one of the following actions:</span></span>  
  
    -   <span data-ttu-id="b4764-119">Salvar os dados no arquivo quando a transformação Cache estiver configurada para gravar dados de uma fonte de dados no fluxo de dados para o gerenciador de conexões de cache.</span><span class="sxs-lookup"><span data-stu-id="b4764-119">Save data to the file when a Cache Transform transformation is configured to write data from a data source in the data flow to the Cache connection manager.</span></span>  
  
    -   <span data-ttu-id="b4764-120">Ler os dados do arquivo de cache.</span><span class="sxs-lookup"><span data-stu-id="b4764-120">Read data from the cache file.</span></span>  
  
     <span data-ttu-id="b4764-121">Para obter mais informações, consulte [Cache Transform](../data-flow/transformations/cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="b4764-121">For more information, see [Cache Transform](../data-flow/transformations/cache-transform.md).</span></span>  
  
-   <span data-ttu-id="b4764-122">Altere os metadados para as colunas armazenadas no cache.</span><span class="sxs-lookup"><span data-stu-id="b4764-122">Change metadata for the columns stored in the cache.</span></span>  
  
-   <span data-ttu-id="b4764-123">Atualize o nome do arquivo de cache no runtime usando uma expressão para definir a propriedade ConnectionString.</span><span class="sxs-lookup"><span data-stu-id="b4764-123">Update the cache file name at runtime by using an expression to set the ConnectionString property.</span></span> <span data-ttu-id="b4764-124">Para obter mais informações, consulte [Usar expressões de propriedade em pacotes](../expressions/use-property-expressions-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="b4764-124">For more information, see [Use Property Expressions in Packages](../expressions/use-property-expressions-in-packages.md).</span></span>  
  
 <span data-ttu-id="b4764-125">Você pode definir propriedades pelo Designer do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="b4764-125">You can set properties through [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="b4764-126">Para obter mais informações sobre as propriedades que podem ser definidas no Designer do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , consulte [Editor do Gerenciador de Conexões de Cache](../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="b4764-126">For more information about the properties that you can set in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Designer, see [Cache Connection Manager Editor](../cache-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="b4764-127">Para obter informações sobre como configurar um gerenciador de conexões de forma programática, consulte <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Adicionar conexões programaticamente](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="b4764-127">For information about how to configure a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="b4764-128">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="b4764-128">Related Tasks</span></span>  
 [<span data-ttu-id="b4764-129">Implementar uma Transformação de Pesquisa em modo de Cache Cheio usando o Gerenciador de Conexões de Cache</span><span class="sxs-lookup"><span data-stu-id="b4764-129">Implement a Lookup Transformation in Full Cache Mode Using the Cache Connection Manager</span></span>](lookup-transformation-full-cache-mode-ole-db-connection-manager.md)  
  
  
