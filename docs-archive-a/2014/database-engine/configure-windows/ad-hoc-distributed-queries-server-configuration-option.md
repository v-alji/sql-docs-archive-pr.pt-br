---
title: Opção de configuração de servidor ad hoc distributed queries | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- OPENROWSET function, ad hoc distributed queries option
- Ad Hoc Distributed Queries option
- ad hoc distributed queries
- 7415 (Database Engine Error)
- OPENDATASOURCE function, ad hoc distributed queries option
- ad hoc access
ms.assetid: 5b982015-e196-44c3-83b8-275fb9d769b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d07b3c038597916cdaf026e24e90aab9d6b61616
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568787"
---
# <a name="ad-hoc-distributed-queries-server-configuration-option"></a><span data-ttu-id="b47b8-102">Opção de configuração de servidor ad hoc distributed queries</span><span class="sxs-lookup"><span data-stu-id="b47b8-102">ad hoc distributed queries Server Configuration Option</span></span>
  <span data-ttu-id="b47b8-103">Por padrão, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não permite consultas distribuídas ad hoc que usam OPENROWSET e OPENDATASOURCE.</span><span class="sxs-lookup"><span data-stu-id="b47b8-103">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not allow ad hoc distributed queries using OPENROWSET and OPENDATASOURCE.</span></span> <span data-ttu-id="b47b8-104">Quando esta opção é definida como 1, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permite acesso ad hoc.</span><span class="sxs-lookup"><span data-stu-id="b47b8-104">When this option is set to 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allows ad hoc access.</span></span> <span data-ttu-id="b47b8-105">Quando esta opção não é definida ou é definida como 0, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não permite o acesso ad hoc.</span><span class="sxs-lookup"><span data-stu-id="b47b8-105">When this option is not set or is set to 0, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not allow ad hoc access.</span></span>  
  
 <span data-ttu-id="b47b8-106">As consultas distribuídas ad hoc usam as funções OPENROWSET e OPENDATASOURCE para se conectarem a fontes de dados remotas que usam OLE DB.</span><span class="sxs-lookup"><span data-stu-id="b47b8-106">Ad hoc distributed queries use the OPENROWSET and OPENDATASOURCE functions to connect to remote data sources that use OLE DB.</span></span> <span data-ttu-id="b47b8-107">OPENROWSET e OPENDATASOURCE devem ser usados apenas para fazer referência a fontes de dados OLE DB que são acessadas com pouca frequência.</span><span class="sxs-lookup"><span data-stu-id="b47b8-107">OPENROWSET and OPENDATASOURCE should be used only to reference OLE DB data sources that are accessed infrequently.</span></span> <span data-ttu-id="b47b8-108">Para qualquer fonte de dados que será acessada muitas vezes, defina um servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="b47b8-108">For any data sources that will be accessed more than several times, define a linked server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b47b8-109">A habilitação do uso de nomes ad hoc indica que qualquer logon autenticado para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pode acessar o provedor.</span><span class="sxs-lookup"><span data-stu-id="b47b8-109">Enabling the use of ad hoc names means that any authenticated login to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can access the provider.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b47b8-110">Os administradores devem habilitar esse recurso para provedores seguros, que podem ser acessados por qualquer logon local.</span><span class="sxs-lookup"><span data-stu-id="b47b8-110">administrators should enable this feature for providers that are safe to be accessed by any local login.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b47b8-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="b47b8-111">Remarks</span></span>  
 <span data-ttu-id="b47b8-112">Tentar fazer uma conexão ad hoc com a opção **Ad Hoc Distributed Queries** não habilitada resultará em erro: Msg 7415, Nível 16, Estado 1, Linha 1</span><span class="sxs-lookup"><span data-stu-id="b47b8-112">Attempting to make an ad hoc connection with **Ad Hoc Distributed Queries** not enabled results in error: Msg 7415, Level 16, State 1, Line 1</span></span>  
  
 <span data-ttu-id="b47b8-113">Acesso ad hoc negado ao provedor OLE DB 'Microsoft.ACE.OLEDB.12.0'.</span><span class="sxs-lookup"><span data-stu-id="b47b8-113">Ad hoc access to OLE DB provider 'Microsoft.ACE.OLEDB.12.0' has been denied.</span></span> <span data-ttu-id="b47b8-114">É necessário acessar esse provedor através de um servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="b47b8-114">You must access this provider through a linked server.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b47b8-115">Exemplos</span><span class="sxs-lookup"><span data-stu-id="b47b8-115">Examples</span></span>  
 <span data-ttu-id="b47b8-116">O exemplo a seguir habilita consultas distribuídas ad hoc e, em seguida, consulta um servidor chamado `Seattle1` usando a função `OPENROWSET` .</span><span class="sxs-lookup"><span data-stu-id="b47b8-116">The following example enables ad hoc distributed queries and then queries a server named `Seattle1` using the `OPENROWSET` function.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
RECONFIGURE;  
sp_configure 'Ad Hoc Distributed Queries', 1;  
RECONFIGURE;  
GO  
  
SELECT a.*  
FROM OPENROWSET('SQLNCLI', 'Server=Seattle1;Trusted_Connection=yes;',  
     'SELECT GroupName, Name, DepartmentID  
      FROM AdventureWorks2012.HumanResources.Department  
      ORDER BY GroupName, Name') AS a;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="b47b8-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b47b8-117">See Also</span></span>  
 <span data-ttu-id="b47b8-118">[Opções de configuração do servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b47b8-118">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="b47b8-119">[Servidores vinculados &#40;Mecanismo de Banco de Dados&#41;](../../relational-databases/linked-servers/linked-servers-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="b47b8-119">[Linked Servers &#40;Database Engine&#41;](../../relational-databases/linked-servers/linked-servers-database-engine.md) </span></span>  
 <span data-ttu-id="b47b8-120">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b47b8-120">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="b47b8-121">[OPENDATASOURCE &#40;Transact-SQL&#41;](/sql/t-sql/functions/opendatasource-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b47b8-121">[OPENDATASOURCE &#40;Transact-SQL&#41;](/sql/t-sql/functions/opendatasource-transact-sql) </span></span>  
 [<span data-ttu-id="b47b8-122">sp_addlinkedserver &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b47b8-122">sp_addlinkedserver &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql)  
  
  
