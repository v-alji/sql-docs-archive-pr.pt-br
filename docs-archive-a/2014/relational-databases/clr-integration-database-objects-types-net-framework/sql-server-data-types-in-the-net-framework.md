---
title: SQL Server tipos de dados no .NET Framework | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- System.Data library
- System.Data.SqlTypes namespace
- data types [CLR integration]
- SqlTypes library
- database objects [CLR integration], data types
- common language runtime [SQL Server], data types
- building database objects [CLR integration], data types
- mapping data types [CLR integration]
ms.assetid: c70d3ffe-2c32-45a5-849b-ef113dda09b9
author: rothja
ms.author: jroth
ms.openlocfilehash: fe0ed680e7050c58738301256575e4138f21276f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685781"
---
# <a name="sql-server-data-types-in-the-net-framework"></a><span data-ttu-id="9177b-102">Tipos de dados do SQL Server no .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9177b-102">SQL Server Data Types in the .NET Framework</span></span>
  <span data-ttu-id="9177b-103">A biblioteca `SqlTypes` faz parte da biblioteca de classe base do [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9177b-103">The `SqlTypes` library is part of the base class library of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span></span> <span data-ttu-id="9177b-104">Ela é projetada para fornecer tipos de dados com a mesma semântica e precisão presentes no banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9177b-104">It is designed to provide data types with the same semantics and precision as those found in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="9177b-105">Este tópico descreve a nova semântica para os programadores do .NET Framework e apresenta os tipos implementados no namespace `System.Data.SqlTypes` incluído na biblioteca `System.Data`.</span><span class="sxs-lookup"><span data-stu-id="9177b-105">This topic describes the new semantics to .NET Framework programmers, and introduces the types implemented in the `System.Data.SqlTypes` namespace that is included in the `System.Data` library.</span></span>  
  
 <span data-ttu-id="9177b-106">A tabela a seguir lista os tópicos desta seção.</span><span class="sxs-lookup"><span data-stu-id="9177b-106">This following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="9177b-107">Comparações de lógica de três valores e nulidade</span><span class="sxs-lookup"><span data-stu-id="9177b-107">Nullability and Three-Value Logic Comparisons</span></span>](nullability-and-three-value-logic-comparisons.md)  
 <span data-ttu-id="9177b-108">Discute como são tratados os valores NULL com tipos de dados de integração CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="9177b-108">Discusses how NULL values are handled with common language runtime (CLR) integration data types.</span></span>  
  
 [<span data-ttu-id="9177b-109">Tipos de dados de integração CLR e ordenação</span><span class="sxs-lookup"><span data-stu-id="9177b-109">Collation and CLR Integration Data Types</span></span>](collation-and-clr-integration-data-types.md)  
 <span data-ttu-id="9177b-110">Descreve como são tratadas as ordenações com integração CLR.</span><span class="sxs-lookup"><span data-stu-id="9177b-110">Describes how collations are handled with CLR integration.</span></span>  
  
 [<span data-ttu-id="9177b-111">Tratando parâmetros de&#41; de LOB &#40;de objeto grande no CLR</span><span class="sxs-lookup"><span data-stu-id="9177b-111">Handling Large Object &#40;LOB&#41; Parameters in the CLR</span></span>](handling-large-object-lob-parameters-in-the-clr.md)  
 <span data-ttu-id="9177b-112">Descreve como passar tipos LOB entre o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e o CLR.</span><span class="sxs-lookup"><span data-stu-id="9177b-112">Describes how to pass LOB types between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the CLR.</span></span>  
  
 [<span data-ttu-id="9177b-113">Mapeando dados de parâmetro CLR</span><span class="sxs-lookup"><span data-stu-id="9177b-113">Mapping CLR Parameter Data</span></span>](mapping-clr-parameter-data.md)  
 <span data-ttu-id="9177b-114">Mostra mapeamentos de tipo de dados entre o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a integração CLR e o .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9177b-114">Shows data type mappings between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], CLR integration, and the .NET Framework.</span></span>  
  
  
