---
title: Programação do procedimento armazenado estendido do Mecanismo de Banco de Dados | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], programming
- stored procedures [SQL Server], extended
- Database Engine [SQL Server], stored procedures
- macros [SQL Server]
- Extended Stored Procedure API [SQL Server]
ms.assetid: 158a6765-0542-4e84-b5ab-f173d946ef5e
author: rothja
ms.author: jroth
ms.openlocfilehash: fecb8f996ddfcaede83cdb330e9c82bffdce5819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583109"
---
# <a name="database-engine-extended-stored-procedure-programming"></a><span data-ttu-id="a22c5-102">Programação do procedimento armazenado estendido do mecanismo do banco de dados</span><span class="sxs-lookup"><span data-stu-id="a22c5-102">Database Engine Extended Stored Procedure Programming</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="a22c5-103">Em vez disso, use a integração CLR.</span><span class="sxs-lookup"><span data-stu-id="a22c5-103">Use CLR Integration instead.</span></span> <span data-ttu-id="a22c5-104">Para obter mais informações, consulte [Conceitos de programação da Integração CLR &#40;Common Language Runtime&#41;](clr-integration/common-language-runtime-clr-integration-programming-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="a22c5-104">For more information, see [Common Language Runtime &#40;CLR&#41; Integration Programming Concepts](clr-integration/common-language-runtime-clr-integration-programming-concepts.md).</span></span>  
  
 <span data-ttu-id="a22c5-105">A [!INCLUDE[msCoName](../includes/msconame-md.md)] API de procedimento armazenado estendido fornece uma API (interface de programação de aplicativo) baseada em servidor para estender a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="a22c5-105">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Extended Stored Procedure API provides a server-based application programming interface (API) for extending [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] functionality.</span></span> <span data-ttu-id="a22c5-106">A API consiste em funções e macros do C e do C++ usadas para compilar aplicativos nas seguintes categorias: procedimentos armazenados estendidos e aplicativos de gateway.</span><span class="sxs-lookup"><span data-stu-id="a22c5-106">The API consists of C and C++ functions and macros used to build applications in the following categories: extended stored procedures and gateway applications.</span></span>  
  
 <span data-ttu-id="a22c5-107">Os procedimentos armazenados estendidos permitem que você crie suas próprias rotinas externas em uma linguagem de programação, como C. Os procedimentos armazenados estendidos aparecem para o usuário como procedimentos armazenados comuns e são executados como estes.</span><span class="sxs-lookup"><span data-stu-id="a22c5-107">Extended stored procedures allow you to create your own external routines in a programming language such as C. The extended stored procedures appear to users as typical stored procedures and are executed in the same way.</span></span> <span data-ttu-id="a22c5-108">Os parâmetros podem ser passados a procedimentos armazenados estendidos e eles podem retornar resultados e status.</span><span class="sxs-lookup"><span data-stu-id="a22c5-108">Parameters can be passed to extended stored procedures, and they can return results and return status.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a22c5-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="a22c5-109">In This Section</span></span>  
 [<span data-ttu-id="a22c5-110">Programando procedimentos armazenados estendidos</span><span class="sxs-lookup"><span data-stu-id="a22c5-110">Programming Extended Stored Procedures</span></span>](extended-stored-procedures-programming/database-engine-extended-stored-procedures-programming.md)  
 <span data-ttu-id="a22c5-111">Explica como criar, gerenciar e usar procedimentos armazenados estendidos.</span><span class="sxs-lookup"><span data-stu-id="a22c5-111">Explains how to create, manage, and use extended stored procedures.</span></span>  
  
 [<span data-ttu-id="a22c5-112">Referência do programador de procedimentos armazenados estendidos</span><span class="sxs-lookup"><span data-stu-id="a22c5-112">Extended Stored Procedures Programmer's Reference</span></span>](extended-stored-procedures-reference/database-engine-extended-stored-procedures-reference.md)  
 <span data-ttu-id="a22c5-113">Contém tópicos de referência da API de procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="a22c5-113">Contains reference topics for the Extended Stored Procedure API.</span></span>  
  
  
