---
title: Agregações CLR definidas pelo usuário | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- aggregate functions [CLR integration]
- custom aggregates [CLR integration]
- calculations [CLR integration]
- user-defined functions [CLR integration]
ms.assetid: bad9b7e8-5967-4afa-8dc8-6d840faf9372
author: rothja
ms.author: jroth
ms.openlocfilehash: d1ef5d07fe082d0eeb2c3484d6e99572d8fc80e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574736"
---
# <a name="clr-user-defined-aggregates"></a><span data-ttu-id="303f9-102">Agregações CLR definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="303f9-102">CLR User-Defined Aggregates</span></span>
  <span data-ttu-id="303f9-103">Funções agregadas executam um cálculo em um conjunto de valores e retornam um único valor.</span><span class="sxs-lookup"><span data-stu-id="303f9-103">Aggregate functions perform a calculation on a set of values and return a single value.</span></span> <span data-ttu-id="303f9-104">Tradicionalmente, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o tem suporte apenas para funções de agregação internas, como `SUM` ou `MAX` , que operam em um conjunto de valores escalares de entrada e geram um único valor agregado a partir desse conjunto.</span><span class="sxs-lookup"><span data-stu-id="303f9-104">Traditionally, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has supported only built-in aggregate functions, such as `SUM` or `MAX`, that operate on a set of input scalar values and generate a single aggregate value from that set.</span></span> <span data-ttu-id="303f9-105">A integração do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com o CLR (common language runtime) do [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework agora permite que os desenvolvedores criem funções de agregação personalizadas no código gerenciado e tornem essas funções acessíveis ao [!INCLUDE[tsql](../../includes/tsql-md.md)] ou a outro código gerenciado.</span><span class="sxs-lookup"><span data-stu-id="303f9-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integration with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework common language runtime (CLR) now allows developers to create custom aggregate functions in managed code, and to make these functions accessible to [!INCLUDE[tsql](../../includes/tsql-md.md)] or other managed code.</span></span>  
  
 <span data-ttu-id="303f9-106">A tabela a seguir lista os tópicos desta seção.</span><span class="sxs-lookup"><span data-stu-id="303f9-106">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="303f9-107">Requisitos para agregações CLR definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="303f9-107">Requirements for CLR User-Defined Aggregates</span></span>](clr-user-defined-aggregates-requirements.md)  
 <span data-ttu-id="303f9-108">Fornece uma visão geral dos requisitos para implementar as funções de agregação definida pelo usuário CLR.</span><span class="sxs-lookup"><span data-stu-id="303f9-108">Provides an overview of the requirements for implementing CLR user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="303f9-109">Invocando funções de agregação CLR definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="303f9-109">Invoking CLR User-Defined Aggregate Functions</span></span>](clr-user-defined-aggregate-invoking-functions.md)  
 <span data-ttu-id="303f9-110">Explica como invocar agregações definidas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="303f9-110">Explains how to invoke user-defined aggregates.</span></span>  
  
  
