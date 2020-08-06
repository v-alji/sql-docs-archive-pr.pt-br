---
title: Constantes grandes são digitadas como tipos de valor grande nos modos de compatibilidade 90 ou posteriores | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- binary constants
- CHARINDEX function
- constants
- character string constants
- PATINDEX function
ms.assetid: 6e309fa0-5fb9-45a1-9739-f13fae525bfe
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 58acde8aaebdcac629463edcfb565eed13355ad4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569823"
---
# <a name="large-constants-are-typed-as-large-value-types-in-90-or-later-compatibility-modes"></a><span data-ttu-id="f10e5-102">Constantes grandes são digitadas como tipos de valor grande no modo de compatibilidade 90 ou posterior</span><span class="sxs-lookup"><span data-stu-id="f10e5-102">Large constants are typed as large-value types in 90 or later compatibility modes</span></span>
  <span data-ttu-id="f10e5-103">O Supervisor de Atualização detectou a presença de constantes grandes.</span><span class="sxs-lookup"><span data-stu-id="f10e5-103">Upgrade Advisor detected the presence of large constants.</span></span> <span data-ttu-id="f10e5-104">Constantes de cadeias de caracteres e constantes binárias maiores que 8.000 bytes são tratadas como tipos de dados de objeto grande no [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f10e5-104">Character string constants and binary constants that are more than 8,000 bytes in size are treated as large object data types in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="f10e5-105">No [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou em versões posteriores, caracteres grandes, Unicode e constantes binárias são digitadas como tipos do valor grande.</span><span class="sxs-lookup"><span data-stu-id="f10e5-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions, large character, Unicode, and binary constants, are typed as large-value types.</span></span>  
  
## <a name="component"></a><span data-ttu-id="f10e5-106">Componente</span><span class="sxs-lookup"><span data-stu-id="f10e5-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="f10e5-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="f10e5-107">Description</span></span>  
 <span data-ttu-id="f10e5-108">Quando funções de cadeia de caracteres, como CHARINDEX e PATINDEX, são usadas com constantes de cadeia de caracteres ou constantes binárias que excedem 8.000 bytes, o [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] retorna o erro 8116, e o [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou versões posteriores retorna o erro 8152.</span><span class="sxs-lookup"><span data-stu-id="f10e5-108">When string functions, such as CHARINDEX and PATINDEX, are used with string or binary constants that exceed 8,000 bytes, [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] returns error number 8116, and [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions return error number 8152.</span></span>  
  
 <span data-ttu-id="f10e5-109">No [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], as funções de cadeia de caracteres retornam o erro 8116 quando são usadas com tipos de dados `text`, `ntext` e `image`.</span><span class="sxs-lookup"><span data-stu-id="f10e5-109">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], the string functions return error 8116 when they are used with the `text`, `ntext`, and `image` data types.</span></span>  
  
 <span data-ttu-id="f10e5-110">No [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou em versões posteriores, as constantes grandes são tratadas como tipos de dados `varchar(max)`, `nvarchar(max)` e `varbinary(max)`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="f10e5-110">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions, the large constants are treated as `varchar(max)`, `nvarchar(max)`, and `varbinary(max)` data types, respectively.</span></span> <span data-ttu-id="f10e5-111">Esses tipos de dados são compatíveis com funções de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f10e5-111">These data types are compatible with string functions.</span></span>  
  
 <span data-ttu-id="f10e5-112">No [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou em versões posteriores, funções de cadeia de caracteres, como CHARINDEX e PATINDEX, assumem a cadeia de caracteres que tem a sequência de caracteres com menos de 8.000 bytes.</span><span class="sxs-lookup"><span data-stu-id="f10e5-112">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions, string functions, such as CHARINDEX and PATINDEX, assume the string that contains the sequence of characters to be found is less than 8,000 bytes.</span></span> <span data-ttu-id="f10e5-113">É pos isso que o erro 8152 é exibido para CHARINDEX e PATINDEX.</span><span class="sxs-lookup"><span data-stu-id="f10e5-113">This is why error 8152 is raised for CHARINDEX and PATINDEX.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f10e5-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f10e5-114">See Also</span></span>  
 <span data-ttu-id="f10e5-115">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="f10e5-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="f10e5-116">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="f10e5-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
