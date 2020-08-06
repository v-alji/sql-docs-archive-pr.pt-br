---
title: MSSQL_ENG014121 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014121 error
ms.assetid: c8595854-cce1-4566-ad64-d565555caded
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 04d4cbdd2197745d2d795814d88c4f7bc28eb90e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568477"
---
# <a name="mssql_eng014121"></a><span data-ttu-id="63763-102">MSSQL_ENG014121</span><span class="sxs-lookup"><span data-stu-id="63763-102">MSSQL_ENG014121</span></span>
    
## <a name="message-details"></a><span data-ttu-id="63763-103">Detalhes da mensagem</span><span class="sxs-lookup"><span data-stu-id="63763-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="63763-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="63763-104">Product Name</span></span>|<span data-ttu-id="63763-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="63763-105">SQL Server</span></span>|  
|<span data-ttu-id="63763-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="63763-106">Event ID</span></span>|<span data-ttu-id="63763-107">14121</span><span class="sxs-lookup"><span data-stu-id="63763-107">14121</span></span>|  
|<span data-ttu-id="63763-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="63763-108">Event Source</span></span>|<span data-ttu-id="63763-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="63763-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="63763-110">Componente</span><span class="sxs-lookup"><span data-stu-id="63763-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="63763-111">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="63763-111">Symbolic Name</span></span>||  
|<span data-ttu-id="63763-112">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="63763-112">Message Text</span></span>|<span data-ttu-id="63763-113">Não foi possível descartar o Distribuidor '%s'.</span><span class="sxs-lookup"><span data-stu-id="63763-113">Could not drop the Distributor '%s'.</span></span> <span data-ttu-id="63763-114">Esse Distribuidor possui bancos de dados de distribuição associados.</span><span class="sxs-lookup"><span data-stu-id="63763-114">This Distributor has associated distribution databases.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="63763-115">Explicação</span><span class="sxs-lookup"><span data-stu-id="63763-115">Explanation</span></span>  
 <span data-ttu-id="63763-116">Uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] configurada como Distribuidor não pode ser removida da função de Distribuidor porque existem bancos de dados de distribuição associados a essa instância.</span><span class="sxs-lookup"><span data-stu-id="63763-116">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is configured as a Distributor cannot be removed from the role of Distributor because there are distribution databases associated with the instance.</span></span> <span data-ttu-id="63763-117">Esse erro ocorre ao tentar descartar um banco de dados de distribuição associado a um ou mais Publicadores.</span><span class="sxs-lookup"><span data-stu-id="63763-117">This error occurs if you attempt to drop a distribution database that is associated with one or more Publishers.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="63763-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="63763-118">User Action</span></span>  
 <span data-ttu-id="63763-119">Para encontrar os nomes de Publicadores e os bancos de dados de distribuição associados a um Distribuidor, execute [sp_helpdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpdistpublisher-transact-sql) em qualquer banco de dados no Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="63763-119">To find the names of any Publishers and distribution databases associated with this Distributor, execute [sp_helpdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpdistpublisher-transact-sql) from any database on the Distributor.</span></span>  
  
 <span data-ttu-id="63763-120">Execute [sp_dropdistributiondb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) em um banco de dados de distribuição associado a esse Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="63763-120">Execute [sp_dropdistributiondb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) for any distribution databases associated with this Distributor.</span></span> <span data-ttu-id="63763-121">Após todas as associações de banco de dados de distribuição serem removidas, é possível desabilitar a distribuição.</span><span class="sxs-lookup"><span data-stu-id="63763-121">After all distribution database associations are removed, you can disable distribution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63763-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="63763-122">See Also</span></span>  
 <span data-ttu-id="63763-123">[Referência de erros e eventos &#40;Replicação&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="63763-123">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="63763-124">Configurar Distribuição</span><span class="sxs-lookup"><span data-stu-id="63763-124">Configure Distribution</span></span>](configure-distribution.md)  
  
  
