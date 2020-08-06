---
title: Tipos de dados de integração de agrupamento e CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- data types [CLR integration]
- parameter collation [CLR integration]
- collations [CLR integration]
ms.assetid: 6ebaed8e-2e2b-4f6d-bf4b-bc25452de441
author: rothja
ms.author: jroth
ms.openlocfilehash: 1a5b0367487aeb80355b8c5c976818e1b6c1ac04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685789"
---
# <a name="collation-and-clr-integration-data-types"></a><span data-ttu-id="b4ac9-102">Tipos de dados de integração CLR e ordenação</span><span class="sxs-lookup"><span data-stu-id="b4ac9-102">Collation and CLR Integration Data Types</span></span>
  <span data-ttu-id="b4ac9-103">No [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], o objeto `CompareInfo` trata as ordenações.</span><span class="sxs-lookup"><span data-stu-id="b4ac9-103">In the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], the `CompareInfo` object handles collations.</span></span> <span data-ttu-id="b4ac9-104">As APIs de cadeia de caracteres do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] usam a propriedade `CompareInfo` associada com o objeto `CultureInfo` do thread atual para executar comparações de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b4ac9-104">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] string application programming interfaces (APIs) use the `CompareInfo` property associated with the `CultureInfo` object of the current thread to perform string comparisons.</span></span> <span data-ttu-id="b4ac9-105">A configuração padrão do `CultureInfo` objeto é baseada na configuração de [!INCLUDE[msCoName](../../includes/msconame-md.md)] localidade do Windows para o computador no qual o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está em execução.</span><span class="sxs-lookup"><span data-stu-id="b4ac9-105">The default setting of the `CultureInfo` object is based on the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows locale setting for the computer on which [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span> <span data-ttu-id="b4ac9-106">Isso determina a semântica de comparação padrão, se nenhum `CultureInfo` explícito for especificado, para comparações de valores de `System.String`.</span><span class="sxs-lookup"><span data-stu-id="b4ac9-106">This determines the default comparison semantics, if no explicit `CultureInfo` is specified, for comparisons of `System.String` values.</span></span> <span data-ttu-id="b4ac9-107">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não altera explicitamente a propriedade `CompareInfo` para a ordenação do servidor ou banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b4ac9-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not explicitly change the `CompareInfo` property to the database or server collation.</span></span> <span data-ttu-id="b4ac9-108">Se necessário, os usuários devem definir a propriedade `CompareInfo` apropriada em suas rotinas.</span><span class="sxs-lookup"><span data-stu-id="b4ac9-108">If required, users must set the appropriate `CompareInfo` property in their routines.</span></span>  
  
## <a name="parameter-collation"></a><span data-ttu-id="b4ac9-109">Ordenação de parâmetros</span><span class="sxs-lookup"><span data-stu-id="b4ac9-109">Parameter Collation</span></span>  
 <span data-ttu-id="b4ac9-110">Quando você cria uma rotina CLR (Common Language Runtime) e um parâmetro de um método CLR associado à rotina é do tipo `SQLString`, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cria uma instância do parâmetro com a ordenação padrão do banco de dados que contém a rotina que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="b4ac9-110">When you create a common language runtime (CLR) routine, and a parameter of a CLR method bound to the routine is of type `SQLString`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creates an instance of the parameter with the default collation of the database containing the calling routine.</span></span> <span data-ttu-id="b4ac9-111">Se um parâmetro não for um `SqlType` (por exemplo, `String` em vez de `SQLString`), as informações de ordenação do banco de dados não são associadas com o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b4ac9-111">If a parameter is not a `SqlType` (for example, `String` rather than `SQLString`), the collation information from the database is not associated with the parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4ac9-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b4ac9-112">See Also</span></span>  
 [<span data-ttu-id="b4ac9-113">Tipos de dados do SQL Server no .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b4ac9-113">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
