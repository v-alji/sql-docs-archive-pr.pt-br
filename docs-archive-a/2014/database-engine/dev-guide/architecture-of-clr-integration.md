---
title: Arquitetura da integração CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], architecture
- architecture [CLR integration]
ms.assetid: 05e4b872-3d21-46de-b4d5-739b5f2a0cf9
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: bb32e2c7f5eb2079146a2fee64af2e2dbc1d3356
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571550"
---
# <a name="architecture-of-clr-integration"></a><span data-ttu-id="32e83-102">Arquitetura da integração CLR</span><span class="sxs-lookup"><span data-stu-id="32e83-102">Architecture of CLR Integration</span></span>
  <span data-ttu-id="32e83-103">A integração do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com o CLR (Common Language Runtime) do .NET Framework permite aos programadores usar linguagens como, por exemplo, Visual C#, Visual Basic .NET e Visual C++.</span><span class="sxs-lookup"><span data-stu-id="32e83-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integration with the .NET Framework common language runtime (CLR) enables database programmers to use languages such as Visual C#, Visual Basic .NET, and Visual C++.</span></span> <span data-ttu-id="32e83-104">Funções, procedimentos armazenados, gatilhos, tipos de dados e agregações estão entre os tipos de lógica corporativa que os programadores podem escrever usando essas linguagens.</span><span class="sxs-lookup"><span data-stu-id="32e83-104">Functions, stored procedures, triggers, data types, and aggregates are among the kinds of business logic that programmers can write with these languages.</span></span>  
  
 <span data-ttu-id="32e83-105">Esta seção descreve a arquitetura da integração do CLR no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e como essa arquitetura fornece um ambiente seguro, escalonável, protegido e eficiente para executar o código do usuário.</span><span class="sxs-lookup"><span data-stu-id="32e83-105">This section describes the architecture of CLR integration inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and how this architecture provides a safe, scalable, secure, and efficient environment to run user code.</span></span>  
  
 <span data-ttu-id="32e83-106">A tabela a seguir lista os tópicos desta seção.</span><span class="sxs-lookup"><span data-stu-id="32e83-106">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="32e83-107">Ambiente hospedado de CLR</span><span class="sxs-lookup"><span data-stu-id="32e83-107">CLR Hosted Environment</span></span>](../../relational-databases/clr-integration/clr-integration-architecture-clr-hosted-environment.md)  
 <span data-ttu-id="32e83-108">Discute as metas do design arquitetônico, os mecanismos e os benefícios da integração do CLR.</span><span class="sxs-lookup"><span data-stu-id="32e83-108">Discusses architectural design goals, mechanisms, and benefits of CLR integration.</span></span>  
  
 [<span data-ttu-id="32e83-109">Desempenho da integração CLR</span><span class="sxs-lookup"><span data-stu-id="32e83-109">Performance of CLR Integration</span></span>](../../relational-databases/clr-integration/clr-integration-architecture-performance.md)  
 <span data-ttu-id="32e83-110">Aborda considerações quanto ao desempenho da arquitetura de integração do CLR.</span><span class="sxs-lookup"><span data-stu-id="32e83-110">Covers performance considerations of the CLR integration architecture.</span></span>  
  
  
