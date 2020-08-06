---
title: Gerenciador de Conexões ADO | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], ADO
- connection managers [Integration Services], ADO
- ADO connection manager [Integration Services]
ms.assetid: 490418bc-5ef1-41b8-a9c8-de38aa96e0f6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fb4b667733f81eebbaf2b6a2ab9b205c09fe2c66
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582093"
---
# <a name="ado-connection-manager"></a><span data-ttu-id="1794c-102">Gerenciador de conexões ADO</span><span class="sxs-lookup"><span data-stu-id="1794c-102">ADO Connection Manager</span></span>
  <span data-ttu-id="1794c-103">Um gerenciador de conexões ADO permite a um pacote se conectar a ActiveX Data Objects (ADO), como um conjunto de registros.</span><span class="sxs-lookup"><span data-stu-id="1794c-103">An ADO connection manager enables a package to connect to ActiveX Data Objects (ADO) objects, such as a recordset.</span></span> <span data-ttu-id="1794c-104">Este gerenciador de conexões é usado tipicamente em tarefas personalizadas escritas em uma versão anterior da linguagem, como o Microsoft Visual Basic 6.0, ou em tarefas personalizadas que são parte de uma aplicação existente que usa ADO para conectar em uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1794c-104">This connection manager is typically used in custom tasks written in an earlier version of a language, such as Microsoft Visual Basic 6.0, or in custom tasks that are part of an existing application that uses ADO to connect to a data source.</span></span>  
  
 <span data-ttu-id="1794c-105">Quando você adiciona um Gerenciador de conexões ADO a um pacote, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] o cria um Gerenciador de conexões que será resolvido para uma conexão ADO em tempo de execução, define as propriedades do Gerenciador de conexões e adiciona o Gerenciador de conexões à `Connections` coleção no pacote.</span><span class="sxs-lookup"><span data-stu-id="1794c-105">When you add an ADO connection manager to a package, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an ADO connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="1794c-106">A propriedade `ConnectionManagerType` do gerenciador de conexões é definida como `ADO`.</span><span class="sxs-lookup"><span data-stu-id="1794c-106">The `ConnectionManagerType` property of the connection manager is set to `ADO`.</span></span>  
  
## <a name="troubleshooting-the-ado-connection-manager"></a><span data-ttu-id="1794c-107">Solucionando problemas do gerenciador de conexões ADO</span><span class="sxs-lookup"><span data-stu-id="1794c-107">Troubleshooting the ADO Connection Manager</span></span>  
 <span data-ttu-id="1794c-108">Ao serem lidos por um gerenciador de conexões ADO, certos tipos de dados de data do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vão gerar os resultados mostrados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="1794c-108">When being read by an ADO connection manager, certain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date data types will generate the results shown in the following table.</span></span>  
  
|<span data-ttu-id="1794c-109">Tipos de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="1794c-109">SQL Server Data type</span></span>|<span data-ttu-id="1794c-110">Result</span><span class="sxs-lookup"><span data-stu-id="1794c-110">Result</span></span>|  
|--------------------------|------------|  
|<span data-ttu-id="1794c-111">`time`, `datetimeoffset`</span><span class="sxs-lookup"><span data-stu-id="1794c-111">`time`, `datetimeoffset`</span></span>|<span data-ttu-id="1794c-112">O pacote apresentará erros, a menos que use comandos com parâmetros SQL.</span><span class="sxs-lookup"><span data-stu-id="1794c-112">The package fails unless the package uses parameterized SQL commands.</span></span> <span data-ttu-id="1794c-113">Para utilizar comandos SQL parametrizados, use a tarefa Executar SQL em seu pacote.</span><span class="sxs-lookup"><span data-stu-id="1794c-113">To use parameterized SQL commands, use the Execute SQL Task in your package.</span></span> <span data-ttu-id="1794c-114">Para obter mais informações, consulte [Tarefa Executar SQL](../control-flow/execute-sql-task.md) e [Parâmetros e códigos de retorno na Tarefa Executar SQL](../parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="1794c-114">For more information, see [Execute SQL Task](../control-flow/execute-sql-task.md) and [Parameters and Return Codes in the Execute SQL Task](../parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>|  
|`datetime2`|<span data-ttu-id="1794c-115">O gerenciador de conexões ADO trunca o valor de milissegundo.</span><span class="sxs-lookup"><span data-stu-id="1794c-115">The ADO connection manager truncates the millisecond value.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="1794c-116">Para obter mais informações sobre tipos de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e como eles são associados a tipos de dados [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], consulte [Tipos de dados &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) e [Tipos de dados do Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="1794c-116">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types and how they map to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data types, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) and [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="configuring-the-ado-connection-manager"></a><span data-ttu-id="1794c-117">Configurando o gerenciador de conexões ADO</span><span class="sxs-lookup"><span data-stu-id="1794c-117">Configuring the ADO Connection Manager</span></span>  
 <span data-ttu-id="1794c-118">Você pode configurar um gerenciador de conexões ADO das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="1794c-118">You can configure an ADO connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="1794c-119">Forneça uma cadeia de conexão específica configurada para atender aos requisitos do provedor selecionado.</span><span class="sxs-lookup"><span data-stu-id="1794c-119">Provide a specific connection string configured to meet the requirements of the selected provider.</span></span>  
  
-   <span data-ttu-id="1794c-120">Dependendo do provedor, inclua o nome da fonte de dados à qual efetuar a conexão.</span><span class="sxs-lookup"><span data-stu-id="1794c-120">Depending on the provider, include the name of the data source to connect to.</span></span>  
  
-   <span data-ttu-id="1794c-121">Forneça credenciais de segurança apropriadas para o provedor selecionado.</span><span class="sxs-lookup"><span data-stu-id="1794c-121">Provide security credentials as appropriate for the selected provider.</span></span>  
  
-   <span data-ttu-id="1794c-122">Indique se a conexão criada a partir do gerenciador de conexões será retida em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="1794c-122">Indicate whether the connection that is created from the connection manager is retained at run time.</span></span>  
  
 <span data-ttu-id="1794c-123">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="1794c-123">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="1794c-124">Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, clique no tópico a seguir:</span><span class="sxs-lookup"><span data-stu-id="1794c-124">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="1794c-125">Configurar Gerenciador de Conexões OLE DB</span><span class="sxs-lookup"><span data-stu-id="1794c-125">Configure OLE DB Connection Manager</span></span>](ole-db-connection-manager.md)  
  
 <span data-ttu-id="1794c-126">Para obter informações sobre como configurar um gerenciador de conexões programaticamente, consulte <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Adicionando conexões programaticamente](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="1794c-126">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1794c-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1794c-127">See Also</span></span>  
 [<span data-ttu-id="1794c-128">Conexões do SSIS &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1794c-128">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
