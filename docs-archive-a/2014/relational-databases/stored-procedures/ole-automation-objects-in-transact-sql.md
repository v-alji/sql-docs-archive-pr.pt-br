---
title: Objetos de automação no Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: conceptual
helpviewer_keywords:
- triggers [SQL Server], OLE Automation
- batches [SQL Server], OLE Automation
- OLE Automation [SQL Server]
- OLE Automation [SQL Server], about OLE Automation
ms.assetid: a887d956-4cd0-400a-aa96-00d7abd7c44b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1f36846565bb60fbf875e9babdabbb6d1667f5ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584112"
---
# <a name="ole-automation-objects-in-transact-sql"></a><span data-ttu-id="1b543-102">Objetos de automação OLE em Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1b543-102">OLE Automation Objects in Transact-SQL</span></span>
  [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="1b543-103">inclui diversos procedimentos armazenados do sistema que permitem que os objetos da Automação OLE sejam mencionados nos lotes, procedimentos armazenados e gatilhos do [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1b543-103">includes several system stored procedures that allow OLE Automation objects to be referenced in [!INCLUDE[tsql](../../includes/tsql-md.md)] batches, stored procedures, and triggers.</span></span> <span data-ttu-id="1b543-104">Esses procedimentos armazenados do sistema são executados como procedimentos armazenados estendidos, e os objetos de automação OLE executados por meio dos procedimentos armazenados são executados no espaço de endereço de uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] da mesma forma que um procedimento armazenado entendido.</span><span class="sxs-lookup"><span data-stu-id="1b543-104">These system stored procedures run as extended stored procedures, and the OLE Automation objects that are executed through the stored procedures run in the address space of an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] in the same way that an extended stored procedure runs.</span></span>  
  
 <span data-ttu-id="1b543-105">Os procedimentos armazenados da Automação OLE permitem que os lotes [!INCLUDE[tsql](../../includes/tsql-md.md)] façam referência aos objetos SQL-DMO e aos objetos da Automação OLE personalizados, como objetos que expõe a interface **IDispatch** .</span><span class="sxs-lookup"><span data-stu-id="1b543-105">The OLE Automation stored procedures enable [!INCLUDE[tsql](../../includes/tsql-md.md)] batches to reference SQL-DMO objects and custom OLE Automation objects, such as objects that expose the **IDispatch** interface.</span></span> <span data-ttu-id="1b543-106">Um servidor OLE personalizado em processo criado com o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] precisa ter um manipulador de erros (especificado com a instrução **On Error GoTo**) para as sub-rotinas **Class_Initialize** e **Class_Terminate**.</span><span class="sxs-lookup"><span data-stu-id="1b543-106">A custom in-process OLE server that is created by using [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] must have an error handler (specified with the **On Error GoTo** statement) for the **Class_Initialize** and **Class_Terminate** subroutines.</span></span> <span data-ttu-id="1b543-107">Erros sem tratamento nas sub-rotinas **Class_Initialize** e **Class_Terminate** podem causar erros imprevisíveis, como uma violação de acesso em uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b543-107">Unhandled errors in the **Class_Initialize** and **Class_Terminate** subroutines can cause unpredictable errors, such as an access violation in an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="1b543-108">Recomendam-se também manipuladores de erro para outras sub-rotinas.</span><span class="sxs-lookup"><span data-stu-id="1b543-108">Error handlers for other subroutines are also recommended.</span></span>  
  
 <span data-ttu-id="1b543-109">A primeira etapa ao usar um objeto de Automação OLE no [!INCLUDE[tsql](../../includes/tsql-md.md)] é chamar o procedimento armazenado do sistema **sp_OACreate** para criar uma instância de objeto no espaço de endereço da instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b543-109">The first step when using an OLE Automation object in [!INCLUDE[tsql](../../includes/tsql-md.md)] is to call the **sp_OACreate** system stored procedure to create an instance of the object in the address space of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="1b543-110">Após uma instância do objeto ter sido criada, chame os seguintes procedimento armazenados para trabalhar com propriedades, métodos e informações de erro referentes ao objeto:</span><span class="sxs-lookup"><span data-stu-id="1b543-110">After an instance of the object has been created, call the following stored procedures to work with the properties, methods, and error information related to the object:</span></span>  
  
-   <span data-ttu-id="1b543-111">**sp_OAGetProperty** obtém o valor de uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="1b543-111">**sp_OAGetProperty** obtains the value of a property.</span></span>  
  
-   <span data-ttu-id="1b543-112">**sp_OASetProperty** define o valor de uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="1b543-112">**sp_OASetProperty** sets the value of a property.</span></span>  
  
-   <span data-ttu-id="1b543-113">**sp_OAMethod** chama um método.</span><span class="sxs-lookup"><span data-stu-id="1b543-113">**sp_OAMethod** calls a method.</span></span>  
  
-   <span data-ttu-id="1b543-114">**sp_OAGetErrorInfo** obtém as informações de erro mais recentes.</span><span class="sxs-lookup"><span data-stu-id="1b543-114">**sp_OAGetErrorInfo** obtains the most recent error information.</span></span>  
  
 <span data-ttu-id="1b543-115">Quando não houver mais necessidade do objeto, chame o **sp_OADestroy** para desalocar a instância do objeto criado usando o **sp_OACreate**.</span><span class="sxs-lookup"><span data-stu-id="1b543-115">When there is no more need for the object, call **sp_OADestroy** to deallocate the instance of the object created by using **sp_OACreate**.</span></span>  
  
 <span data-ttu-id="1b543-116">Objetos de automação OLE retornam dados através de valores de propriedade e métodos.</span><span class="sxs-lookup"><span data-stu-id="1b543-116">OLE Automation objects return data through property values and methods.</span></span> <span data-ttu-id="1b543-117">**sp_OAGetProperty** e **sp_OAMethod** retornam esses valores de dados no formato de um conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="1b543-117">**sp_OAGetProperty** and **sp_OAMethod** return these data values in the form of a result set.</span></span>  
  
 <span data-ttu-id="1b543-118">O escopo de um objeto de automação OLE é um lote.</span><span class="sxs-lookup"><span data-stu-id="1b543-118">The scope of an OLE Automation object is a batch.</span></span> <span data-ttu-id="1b543-119">Todas as referências a um objeto devem estar contidas em um único lote, procedimento armazenado ou gatilho.</span><span class="sxs-lookup"><span data-stu-id="1b543-119">All references to the object must be contained in a single batch, stored procedure, or trigger.</span></span>  
  
 <span data-ttu-id="1b543-120">Quando se referem aos objetos, os objetos de automação OLE [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dão suporte ao desvio do referido objeto a outros objetos existentes nele.</span><span class="sxs-lookup"><span data-stu-id="1b543-120">When it references objects, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] OLE Automation objects support traversing the referenced object to other objects that it contains.</span></span> <span data-ttu-id="1b543-121">Por exemplo, ao usar o objeto SQL-DMO **SQLServer** , é possível fazer referência a bancos de dados e tabelas contidos nesse servidor.</span><span class="sxs-lookup"><span data-stu-id="1b543-121">For example, when using the SQL-DMO **SQLServer** object, references can be made to databases and tables contained on that server.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="1b543-122">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="1b543-122">Related Content</span></span>  
 [<span data-ttu-id="1b543-123">Sintaxe da hierarquia de objetos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1b543-123">Object Hierarchy Syntax &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/object-hierarchy-syntax-transact-sql)  
  
 [<span data-ttu-id="1b543-124">Configuração da Área de Superfície</span><span class="sxs-lookup"><span data-stu-id="1b543-124">Surface Area Configuration</span></span>](../security/surface-area-configuration.md)  
  
 [<span data-ttu-id="1b543-125">Opção de configuração de servidor Ole Automation Procedures</span><span class="sxs-lookup"><span data-stu-id="1b543-125">Ole Automation Procedures Server Configuration Option</span></span>](../../database-engine/configure-windows/ole-automation-procedures-server-configuration-option.md)  
  
 [<span data-ttu-id="1b543-126">sp_OACreate &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1b543-126">sp_OACreate &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oacreate-transact-sql)  
  
 [<span data-ttu-id="1b543-127">sp_OAGetProperty &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1b543-127">sp_OAGetProperty &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oagetproperty-transact-sql)  
  
 [<span data-ttu-id="1b543-128">sp_OASetProperty &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1b543-128">sp_OASetProperty &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oasetproperty-transact-sql)  
  
 [<span data-ttu-id="1b543-129">sp_OAMethod &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1b543-129">sp_OAMethod &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oamethod-transact-sql)  
  
 [<span data-ttu-id="1b543-130">sp_OAGetErrorInfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1b543-130">sp_OAGetErrorInfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oageterrorinfo-transact-sql)  
  
 [<span data-ttu-id="1b543-131">sp_OADestroy &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1b543-131">sp_OADestroy &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oadestroy-transact-sql)  
  
  
