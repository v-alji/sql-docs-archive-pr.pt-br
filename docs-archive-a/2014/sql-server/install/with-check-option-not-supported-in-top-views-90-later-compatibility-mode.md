---
title: Não há suporte para WITH CHECK OPTION em exibições que contenham TOP nos modos de compatibilidade 90 ou posteriores | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- TOP clause
- WITH CHECK OPTION clause
ms.assetid: 1b9581d0-bad9-43e0-b8fc-f32d8a8a04ca
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ee7775c875e33f104341a1da39f5fe6c9326f284
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573388"
---
# <a name="with-check-option-is-not-supported-in-views-that-contain-top-in-90-or-later-compatibility-modes"></a><span data-ttu-id="0d359-102">Não há suporte para WITH CHECK OPTION em exibições que contenham TOP no modo de compatibilidade 90 ou posterior</span><span class="sxs-lookup"><span data-stu-id="0d359-102">WITH CHECK OPTION is not supported in views that contain TOP in 90 or later compatibility modes</span></span>
  <span data-ttu-id="0d359-103">O Supervisor de Atualização detectou uma exibição que usa o WITH CHECK OPTION e uma cláusula TOP na instrução SELECT da exibição ou em uma exibição referenciada.</span><span class="sxs-lookup"><span data-stu-id="0d359-103">Upgrade Advisor detected a view that uses the WITH CHECK OPTION and a TOP clause in the SELECT statement of the view or in a referenced view.</span></span> <span data-ttu-id="0d359-104">Exibições definidas dessa forma permitem, incorretamente, que os dados sejam modificados através da exibição; isso pode gerar resultados imprecisos quando o modo de compatibilidade do banco de dados está definido como 80 ou anterior.</span><span class="sxs-lookup"><span data-stu-id="0d359-104">Views defined this way incorrectly allow data to be modified through the view and may produce inaccurate results when the database compatibility mode is set to 80 and earlier.</span></span> <span data-ttu-id="0d359-105">Não é possível inserir ou atualizar dados através de uma exibição que usa WITH CHECK OPTION quando a exibição ou uma exibição referenciada usa a cláusula TOP e o modo de compatibilidade do banco de dados está definido como 90 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="0d359-105">Data cannot be inserted or updated through a view that uses WITH CHECK OPTION when the view or a referenced view uses the TOP clause and the database compatibility mode is set to 90 or later.</span></span>  
  
## <a name="component"></a><span data-ttu-id="0d359-106">Componente</span><span class="sxs-lookup"><span data-stu-id="0d359-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="0d359-107">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="0d359-107">Corrective Action</span></span>  
 <span data-ttu-id="0d359-108">Quando você faz a atualização, os bancos de dados de usuários mantêm seus modos de compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="0d359-108">When you upgrade, user databases maintain their compatibility mode.</span></span> <span data-ttu-id="0d359-109">Antes de alterar o modo de compatibilidade do banco de dados para 100 ou posterior, modifique as exibições que usam tanto WITH CHECK OPTION quanto TOP caso precise alterar dados através da exibição.</span><span class="sxs-lookup"><span data-stu-id="0d359-109">Before you change the database compatibility mode to 100 or later, modify views that use both WITH CHECK OPTION and TOP if data modification through the view is required.</span></span> <span data-ttu-id="0d359-110">Para obter mais informações, consulte [sp_dbcmptlevel &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-dbcmptlevel-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0d359-110">For more information, see [sp_dbcmptlevel &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dbcmptlevel-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d359-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0d359-111">See Also</span></span>  
 <span data-ttu-id="0d359-112">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="0d359-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="0d359-113">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="0d359-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
