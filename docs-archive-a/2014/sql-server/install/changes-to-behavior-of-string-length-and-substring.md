---
title: Alterações no comportamento de String-Length e substring | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 2119b7ba-2e52-44bf-ac57-82c2d46a48ff
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 1188823a877b4c5dc9cef13431492dfe3b303e23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573519"
---
# <a name="changes-to-behavior-of-string-length-and-substring"></a><span data-ttu-id="94bd8-102">Alterações no comportamento de string-length e substring</span><span class="sxs-lookup"><span data-stu-id="94bd8-102">Changes to behavior of string-length and substring</span></span>
  <span data-ttu-id="94bd8-103">A [função de comprimento da cadeia de caracteres &#40;xquery&#41;](/sql/xquery/functions-on-string-values-string-length) e a [função substring &#40;funções do XQuery&#41;](/sql/xquery/functions-on-string-values-substring) podem retornar resultados diferentes quando usadas com bancos de dados XML que contêm caracteres substitutos.</span><span class="sxs-lookup"><span data-stu-id="94bd8-103">The [string-length Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-string-length) and [substring Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-substring) functions may return different results when used with XML databases that contain surrogate characters.</span></span>  
  
## <a name="description"></a><span data-ttu-id="94bd8-104">Descrição</span><span class="sxs-lookup"><span data-stu-id="94bd8-104">Description</span></span>  
 <span data-ttu-id="94bd8-105">Quando um banco de dados é definido para ser compatível com [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , o comportamento da [função de comprimento da cadeia de caracteres &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-string-length) e a [função substring &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-substring) funções são alteradas ao lidar com caracteres suplementares Unicode.</span><span class="sxs-lookup"><span data-stu-id="94bd8-105">When a database is set to be compatible with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], the behavior of the [string-length Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-string-length) and [substring Function &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-substring) functions changes when dealing with Unicode supplementary characters.</span></span> <span data-ttu-id="94bd8-106">Cada caractere suplementar Unicode definido para ter um ponto de código maior que U+FFFF, é contado como um caractere por essas funções, em vez de dois, como era contado em versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="94bd8-106">Each Unicode supplementary character, which is defined by having a code point larger than U+FFFF, is counted as one character by these functions rather than two, as it was in previous versions.</span></span>  
  
 <span data-ttu-id="94bd8-107">Para obter mais informações sobre caracteres substitutos, consulte [Surrogates and Supplementary Characters](https://go.microsoft.com/fwlink/?LinkId=178317)(em inglês).</span><span class="sxs-lookup"><span data-stu-id="94bd8-107">For more information about surrogate characters, see [Surrogates and Supplementary Characters](https://go.microsoft.com/fwlink/?LinkId=178317).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94bd8-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="94bd8-108">See Also</span></span>  
 <span data-ttu-id="94bd8-109">[Problemas de atualização do Mecanismo de Banco de Dados](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="94bd8-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="94bd8-110">Supervisor de atualização do SQL Server 2014 &#91;novo&#93;</span><span class="sxs-lookup"><span data-stu-id="94bd8-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](https://docs.microsoft.com/sql/sql-server/install/sql-server-2014-upgrade-advisor)  
  
  
