---
title: Características de execução de procedimentos armazenados estendidos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], executing
- executing extended stored procedures [SQL Server]
ms.assetid: 6fe1f7e8-cc02-49df-8a2a-d47a96ec3567
author: rothja
ms.author: jroth
ms.openlocfilehash: edbd73797699d65f694e91bc3035e0dc9366c9d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570027"
---
# <a name="execution-characteristics-of-extended-stored-procedures"></a><span data-ttu-id="adecc-102">Características de execução de procedimentos armazenados estendidos</span><span class="sxs-lookup"><span data-stu-id="adecc-102">Execution Characteristics of Extended Stored Procedures</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="adecc-103">Em vez disso, use a integração CLR.</span><span class="sxs-lookup"><span data-stu-id="adecc-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="adecc-104">A execução de um procedimento armazenado estendido tem as seguintes características:</span><span class="sxs-lookup"><span data-stu-id="adecc-104">The execution of an extended stored procedure has these characteristics:</span></span>  
  
-   <span data-ttu-id="adecc-105">A função de procedimento armazenado estendido é executada no contexto de segurança do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="adecc-105">The extended stored procedure function is executed under the security context of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="adecc-106">A função de procedimento armazenado estendido é executada no espaço de processo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="adecc-106">The extended stored procedure function runs in the process space of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="adecc-107">O thread associado com a execução do procedimento armazenado estendido é igual ao usado na conexão do cliente.</span><span class="sxs-lookup"><span data-stu-id="adecc-107">The thread associated with the execution of the extended stored procedure is the same one used for the client connection.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="adecc-108">Antes de adicionar procedimentos armazenados estendidos ao servidor e conceder permissões de execução a outros usuários, o administrador do sistema deve examinar detalhadamente cada procedimento armazenado estendido para certificar-se de que ele não contém código nocivo ou mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="adecc-108">Before adding extended stored procedures to the server and granting execute permissions to other users, the system administrator should thoroughly review each extended stored procedure to make sure that it does not contain harmful or malicious code.</span></span>  
  
-  
  
 <span data-ttu-id="adecc-109">Depois que a DLL de procedimento armazenado estendido é carregada, a DLL permanece carregada no espaço de endereço do servidor até que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o seja interrompido ou o administrador descarregue explicitamente a DLL usando DBCC *dll_name* (gratuito).</span><span class="sxs-lookup"><span data-stu-id="adecc-109">After the extended stored procedure DLL is loaded, the DLL remains loaded in the address space of the server until [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is stopped or the administrator explicitly unloads the DLL by using DBCC *DLL_name* (FREE).</span></span>  
  
 <span data-ttu-id="adecc-110">O procedimento armazenado estendido pode ser executado a partir do [!INCLUDE[tsql](../../includes/tsql-md.md)] como um procedimento armazenado usando a instrução EXECUTE:</span><span class="sxs-lookup"><span data-stu-id="adecc-110">The extended stored procedure can be executed from [!INCLUDE[tsql](../../includes/tsql-md.md)] as a stored procedure by using the EXECUTE statement:</span></span>  
  
```  
EXECUTE @retval = xp_extendedProcName @param1, @param2 OUTPUT  
```  
  
## <a name="parameters"></a><span data-ttu-id="adecc-111">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="adecc-111">Parameters</span></span>  
 <span data-ttu-id="adecc-112">\@ *retval*</span><span class="sxs-lookup"><span data-stu-id="adecc-112">\@ *retval*</span></span>  
 <span data-ttu-id="adecc-113">É um valor de retorno.</span><span class="sxs-lookup"><span data-stu-id="adecc-113">Is a return value.</span></span>  
  
 <span data-ttu-id="adecc-114">\@*param1*</span><span class="sxs-lookup"><span data-stu-id="adecc-114">\@ *param1*</span></span>  
 <span data-ttu-id="adecc-115">É um parâmetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="adecc-115">Is an input parameter.</span></span>  
  
 <span data-ttu-id="adecc-116">\@*param2*</span><span class="sxs-lookup"><span data-stu-id="adecc-116">\@ *param2*</span></span>  
 <span data-ttu-id="adecc-117">É um parâmetro de entrada/saída.</span><span class="sxs-lookup"><span data-stu-id="adecc-117">Is an input/output parameter.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="adecc-118">Os procedimentos armazenados estendidos oferecem aprimoramentos de desempenho e estendem a funcionalidade do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="adecc-118">Extended stored procedures offer performance enhancements and extend [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] functionality.</span></span> <span data-ttu-id="adecc-119">Porém, como a DLL do procedimento armazenado estendido e o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] compartilham o mesmo espaço de endereço, um procedimento problemático pode afetar adversamente o funcionamento do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="adecc-119">However, because the extended stored procedure DLL and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] share the same address space, a problem procedure can adversely affect [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] functioning.</span></span> <span data-ttu-id="adecc-120">Embora as exceções lançadas pela DLL do procedimento armazenado estendido sejam tratadas pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], é possível danificar áreas de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="adecc-120">Although exceptions thrown by the extended stored procedure DLL are handled by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it is possible to damage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data areas.</span></span> <span data-ttu-id="adecc-121">Como precaução de segurança, apenas os administradores do sistema do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podem adicionar procedimentos armazenados estendidos ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="adecc-121">As a security precaution, only [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrators can add extended stored procedures to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="adecc-122">Esses procedimentos devem ser extensivamente testados antes ser instalados.</span><span class="sxs-lookup"><span data-stu-id="adecc-122">These procedures should be thoroughly tested before they are installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adecc-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="adecc-123">See Also</span></span>  
 <span data-ttu-id="adecc-124">[Programando procedimentos armazenados estendidos](database-engine-extended-stored-procedures-programming.md) </span><span class="sxs-lookup"><span data-stu-id="adecc-124">[Programming Extended Stored Procedures](database-engine-extended-stored-procedures-programming.md) </span></span>  
 [<span data-ttu-id="adecc-125">Consulta de procedimentos armazenados estendidos no SQL Server</span><span class="sxs-lookup"><span data-stu-id="adecc-125">Querying Extended Stored Procedures Installed in SQL Server</span></span>](querying-extended-stored-procedures-installed-in-sql-server.md)  
  
  
