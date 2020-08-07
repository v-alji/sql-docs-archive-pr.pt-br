---
title: Funções CLR definidas pelo usuário | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- building database objects [CLR integration], user-defined functions
- functions [CLR integration]
- common language runtime [SQL Server], user-defined functions
- database objects [CLR integration], user-defined functions
- user-defined functions [CLR integration]
ms.assetid: 6f7491f1-9a46-4146-ae09-056248634de2
author: rothja
ms.author: jroth
ms.openlocfilehash: ba7a4a983ec0cb36ef0fd79df44491f7f23f7648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576453"
---
# <a name="clr-user-defined-functions"></a><span data-ttu-id="47d56-102">Funções CLR definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="47d56-102">CLR User-Defined Functions</span></span>
  <span data-ttu-id="47d56-103">As funções definidas pelo usuário são rotinas que podem obter parâmetros, executar cálculos ou outras ações e retornar um resultado.</span><span class="sxs-lookup"><span data-stu-id="47d56-103">User-defined functions are routines that can take parameters, perform calculations or other actions, and return a result.</span></span> <span data-ttu-id="47d56-104">A partir do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], é possível escrever funções definidas pelo usuário em qualquer linguagem de programação do [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework, como o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET ou o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="47d56-104">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], you can write user-defined functions in any [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework programming language, such as [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#.</span></span>  
  
 <span data-ttu-id="47d56-105">Há dois tipos de funções: escalar, que retorna um único valor, e com valor de tabela, que retorna um conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="47d56-105">There are two types of functions: scalar, which returns a single value, and table-valued, which returns a set of rows.</span></span>  
  
 <span data-ttu-id="47d56-106">A tabela a seguir lista os tópicos desta seção.</span><span class="sxs-lookup"><span data-stu-id="47d56-106">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="47d56-107">Funções de valor escalar CLR</span><span class="sxs-lookup"><span data-stu-id="47d56-107">CLR Scalar-Valued Functions</span></span>](clr-scalar-valued-functions.md)  
 <span data-ttu-id="47d56-108">Abrange requisitos de implementação e exemplos de funções com valor escalar.</span><span class="sxs-lookup"><span data-stu-id="47d56-108">Covers implementation requirements and examples of scalar-valued functions.</span></span>  
  
 [<span data-ttu-id="47d56-109">Funções com valor de tabela CLR</span><span class="sxs-lookup"><span data-stu-id="47d56-109">CLR Table-Valued Functions</span></span>](clr-table-valued-functions.md)  
 <span data-ttu-id="47d56-110">Aborda como implementar e usar funções com valor de tabela (TVFs), além das diferenças entre TVFs CLR e [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47d56-110">Discusses how to implement and use table-valued functions (TVFs), as well as differences between [!INCLUDE[tsql](../../includes/tsql-md.md)] and common language runtime (CLR) TVFs.</span></span>  
  
 [<span data-ttu-id="47d56-111">Agregações CLR definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="47d56-111">CLR User-Defined Aggregates</span></span>](clr-user-defined-aggregates.md)  
 <span data-ttu-id="47d56-112">Descreve como implementar e usar agregações definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="47d56-112">Describes how to implement and use user-defined aggregates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47d56-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="47d56-113">See Also</span></span>  
 [<span data-ttu-id="47d56-114">Funções definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="47d56-114">User-Defined Functions</span></span>](../user-defined-functions/user-defined-functions.md)  
  
  
