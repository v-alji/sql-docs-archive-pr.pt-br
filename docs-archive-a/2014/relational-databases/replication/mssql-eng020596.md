---
title: MSSQL_ENG020596 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020596 error
ms.assetid: fa33627c-2e99-4be3-9424-52ab83446e07
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8b1c61f3683442e0d474ff36a65c89446dbd7bd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583528"
---
# <a name="mssql_eng020596"></a><span data-ttu-id="683e0-102">MSSQL_ENG020596</span><span class="sxs-lookup"><span data-stu-id="683e0-102">MSSQL_ENG020596</span></span>
    
## <a name="message-details"></a><span data-ttu-id="683e0-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="683e0-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="683e0-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="683e0-104">Product Name</span></span>|<span data-ttu-id="683e0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="683e0-105">SQL Server</span></span>|  
|<span data-ttu-id="683e0-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="683e0-106">Event ID</span></span>|<span data-ttu-id="683e0-107">20596</span><span class="sxs-lookup"><span data-stu-id="683e0-107">20596</span></span>|  
|<span data-ttu-id="683e0-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="683e0-108">Event Source</span></span>|<span data-ttu-id="683e0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="683e0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="683e0-110">Componente</span><span class="sxs-lookup"><span data-stu-id="683e0-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="683e0-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="683e0-111">Symbolic Name</span></span>||  
|<span data-ttu-id="683e0-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="683e0-112">Message Text</span></span>|<span data-ttu-id="683e0-113">Somente '%s' ou membros de db_owner podem descartar o agente anônimo.</span><span class="sxs-lookup"><span data-stu-id="683e0-113">Only '%s' or members of db_owner can drop the anonymous agent.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="683e0-114">Explicação</span><span class="sxs-lookup"><span data-stu-id="683e0-114">Explanation</span></span>  
 <span data-ttu-id="683e0-115">Você não tem permissões adequadas para descartar o agente da assinatura anônima.</span><span class="sxs-lookup"><span data-stu-id="683e0-115">You do not have sufficient permissions to drop the agent for the anonymous subscription.</span></span> <span data-ttu-id="683e0-116">O logon usado para chamar [sp_dropanonymousagent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropanonymousagent-transact-sql) deve ser um membro da função de servidor fixa **sysadmin** no Distribuidor ou da função de banco de dados fixa **db_owner** no banco de dados de distribuição ou, então, o usuário deve ter iniciado a primeira execução do agente.</span><span class="sxs-lookup"><span data-stu-id="683e0-116">The login used when calling [sp_dropanonymousagent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropanonymousagent-transact-sql) must be a member of the **sysadmin** fixed server role at the Distributor or **db_owner** fixed database role in the distribution database, or the user must be the one that initiated the first run of the agent.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="683e0-117">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="683e0-117">User Action</span></span>  
 <span data-ttu-id="683e0-118">Efetue logon com as credenciais apropriadas e execute **sp_dropanonymousagent**.</span><span class="sxs-lookup"><span data-stu-id="683e0-118">Login with the appropriate credentials, and execute **sp_dropanonymousagent**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="683e0-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="683e0-119">See Also</span></span>  
 [<span data-ttu-id="683e0-120">Referência de erros e eventos &#40;Replicação&#41;</span><span class="sxs-lookup"><span data-stu-id="683e0-120">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
