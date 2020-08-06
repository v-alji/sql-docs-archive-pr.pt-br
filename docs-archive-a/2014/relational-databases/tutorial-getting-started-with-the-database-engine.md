---
title: 'Tutorial: introdução ao Mecanismo de Banco de Dados | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- tutorials [connecting]
- tutorials [Database Engine]
- unable to connect [SQL Server]
- failure to connect [SQL Server]
- connecting tutorial [SQL Server]
ms.assetid: 655e709b-346b-469c-bddc-a5a0238d07e0
author: rothja
ms.author: jroth
ms.openlocfilehash: aaa1fb21c026d064c2b14db73aadc2b82e9c15d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582857"
---
# <a name="tutorial-getting-started-with-the-database-engine"></a><span data-ttu-id="b612a-102">Tutorial: introdução ao Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="b612a-102">Tutorial: Getting Started with the Database Engine</span></span>
  <span data-ttu-id="b612a-103">Bem-vindo ao Guia de Introdução com o tutorial [!INCLUDE[ssDE](../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b612a-103">Welcome to the Getting Started with the [!INCLUDE[ssDE](../includes/ssde-md.md)] tutorial.</span></span> <span data-ttu-id="b612a-104">Este tutorial é dirigido a usuários não familiarizados com o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e que instalaram o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou [!INCLUDE[ssExpress](../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b612a-104">This tutorial is intended for users who are new to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and who have installed [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or [!INCLUDE[ssExpress](../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="b612a-105">Este tutorial resumido ajuda você a começar a usar o [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b612a-105">This brief tutorial helps you get started using the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="b612a-106">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="b612a-106">What You Will Learn</span></span>  
 <span data-ttu-id="b612a-107">Este tutorial mostra como se conectar ao [!INCLUDE[ssDE](../includes/ssde-md.md)] usando o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , tanto no computador local quanto em outro computador.</span><span class="sxs-lookup"><span data-stu-id="b612a-107">This tutorial shows you how to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] on both the local computer and from another computer.</span></span>  
  
 <span data-ttu-id="b612a-108">Este tutorial é dividido em duas lições:</span><span class="sxs-lookup"><span data-stu-id="b612a-108">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="b612a-109">Lição 1: conectando-se ao Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="b612a-109">Lesson 1: Connecting to the Database Engine</span></span>](lesson-1-connecting-to-the-database-engine.md)  
 <span data-ttu-id="b612a-110">Nesta lição, você aprenderá a se conectar ao [!INCLUDE[ssDE](../includes/ssde-md.md)] e permitir que mais pessoas se conectem.</span><span class="sxs-lookup"><span data-stu-id="b612a-110">In this lesson, you will learn how to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] and enable additional people to connect.</span></span>  
  
 [<span data-ttu-id="b612a-111">Lição 2: Conectando de outro computador</span><span class="sxs-lookup"><span data-stu-id="b612a-111">Lesson 2: Connecting from Another Computer</span></span>](lesson-2-connecting-from-another-computer.md)  
 <span data-ttu-id="b612a-112">Nesta lição, você aprenderá a conectar ao [!INCLUDE[ssDE](../includes/ssde-md.md)] de um segundo computador, inclusive a habilitar protocolos configurando portas, a e configurar as configurações de firewall.</span><span class="sxs-lookup"><span data-stu-id="b612a-112">In this lesson, you will learn how to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] from a second computer, including enabling protocols, configuring ports, and configuring firewall settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b612a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b612a-113">Requirements</span></span>  
 <span data-ttu-id="b612a-114">Este tutorial não exige pré-requisitos de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="b612a-114">This tutorial has no knowledge prerequisites.</span></span>  
  
 <span data-ttu-id="b612a-115">Para que você possa usar o tutorial, os itens a seguir devem estar instalados no sistema:</span><span class="sxs-lookup"><span data-stu-id="b612a-115">Your system must have the following installed to use this tutorial:</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]<span data-ttu-id="b612a-116">.</span><span class="sxs-lookup"><span data-stu-id="b612a-116">.</span></span> [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] <span data-ttu-id="b612a-117">pode ser instalado executando a instalação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou baixando e instalando do [Centro de Download da Microsoft](https://go.microsoft.com/fwlink/?LinkId=144346).</span><span class="sxs-lookup"><span data-stu-id="b612a-117">can be installed by running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] setup or by downloading and installing from [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=144346).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b612a-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b612a-118">See Also</span></span>  
 [<span data-ttu-id="b612a-119">Tutorial: SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b612a-119">Tutorial: SQL Server Management Studio</span></span>](../ssms/tutorials/tutorial-sql-server-management-studio.md)  
  
  
