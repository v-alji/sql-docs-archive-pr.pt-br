---
title: Remover dois pontos após a palavra-chave reservada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- reserved keywords
ms.assetid: 4f23f7e4-7b4d-4e19-86c9-7527bb8b107d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fc6882439338509a3c716129d9504f209ab1e555
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686052"
---
# <a name="remove-colon-following-reserved-keyword"></a><span data-ttu-id="dc8af-102">Remover dois-pontos após palavra-chave reservada</span><span class="sxs-lookup"><span data-stu-id="dc8af-102">Remove colon following reserved keyword</span></span>
  <span data-ttu-id="dc8af-103">O Supervisor de Atualização detectou um script que contém dois-pontos (:) depois de uma palavra-chave reservada.</span><span class="sxs-lookup"><span data-stu-id="dc8af-103">The Upgrade Advisor detected a script that contains a colon (:) following a reserved keyword.</span></span> <span data-ttu-id="dc8af-104">Em versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], essa sintaxe era ignorada e as instruções eram executadas corretamente.</span><span class="sxs-lookup"><span data-stu-id="dc8af-104">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this syntax is ignored and the statements execute successfully.</span></span> <span data-ttu-id="dc8af-105">Agora, essa sintaxe faz com que a instrução falhe quando o modo de compatibilidade de banco de dados está definido como 100 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="dc8af-105">Now, this syntax causes the statement to fail when the database compatibility mode is set to 100 or later.</span></span>  
  
 <span data-ttu-id="dc8af-106">Os bancos de dados de usuário mantêm o modo de compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="dc8af-106">User databases maintain their compatibility mode.</span></span>  
  
## <a name="component"></a><span data-ttu-id="dc8af-107">Componente</span><span class="sxs-lookup"><span data-stu-id="dc8af-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="dc8af-108">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="dc8af-108">Corrective Action</span></span>  
 <span data-ttu-id="dc8af-109">Antes de alterar o modo de compatibilidade do banco de dados para 100 ou posterior, modifique seus scripts removendo os dois-pontos depois das palavras-chave reservadas.</span><span class="sxs-lookup"><span data-stu-id="dc8af-109">Before you change the database compatibility mode to 100 or later, modify your scripts by removing colons that follow reserved keywords.</span></span> <span data-ttu-id="dc8af-110">Para obter mais informações, consulte ‘sp_dbcmptlevel’ nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dc8af-110">For more information, see "sp_dbcmptlevel" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc8af-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="dc8af-111">See Also</span></span>  
 <span data-ttu-id="dc8af-112">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="dc8af-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="dc8af-113">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="dc8af-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
