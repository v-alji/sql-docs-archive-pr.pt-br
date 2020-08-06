---
title: 'Tutorial: Orientador de Otimização do Mecanismo de Banco de Dados | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- Database Engine Tuning Advisor [SQL Server], tutorials
- tutorials [Database Engine Tuning Advisor]
ms.assetid: 3b54cbbe-d8c6-424d-92f1-aa58179f4da8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 68e026cb28b875b834f20c906232285ede8e217b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569794"
---
# <a name="tutorial-database-engine-tuning-advisor"></a><span data-ttu-id="a820d-102">Tutorial: Database Engine Tuning Advisor</span><span class="sxs-lookup"><span data-stu-id="a820d-102">Tutorial: Database Engine Tuning Advisor</span></span>
  <span data-ttu-id="a820d-103">Bem-vindo ao tutorial do Orientador de Otimização do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="a820d-103">Welcome to the Database Engine Tuning Advisor tutorial.</span></span> <span data-ttu-id="a820d-104">O Orientador de Otimização do Mecanismo de Banco de Dados examina como são processadas as consultas nos bancos de dados que você especifica e recomenda meios de aprimorar o desempenho de processamento de consultas, modificando as estruturas do banco de dados, como índices, exibições indexadas e particionamento.</span><span class="sxs-lookup"><span data-stu-id="a820d-104">Database Engine Tuning Advisor examines how queries are processed in the databases you specify, and then recommends how you can improve query processing performance by modifying database structures such as indexes, indexed views, and partitioning.</span></span>  
  
 <span data-ttu-id="a820d-105">O Orientador de Otimização do Mecanismo de Banco de Dados fornece duas interfaces do usuário: uma GUI (interface gráfica do usuário) e o utilitário de prompt de comando **dta** .</span><span class="sxs-lookup"><span data-stu-id="a820d-105">Database Engine Tuning Advisor provides two user interfaces: a graphical user interface (GUI) and the **dta** command prompt utility.</span></span> <span data-ttu-id="a820d-106">A GUI facilita a exibição rápida dos resultados das sessões de ajuste, enquanto o utilitário **dta** facilita a inserção da funcionalidade Orientador de Otimização do Mecanismo de Banco de Dados em scripts para ajuste automatizado.</span><span class="sxs-lookup"><span data-stu-id="a820d-106">The GUI makes it easy to quickly view the results of tuning sessions, and the **dta** utility makes it easy to incorporate Database Engine Tuning Advisor functionality into scripts for automated tuning.</span></span> <span data-ttu-id="a820d-107">Além disso, o Orientador de Otimização do Mecanismo de Banco de Dados aceita entrada XML, o que oferece mais controle sobre o processo de ajuste.</span><span class="sxs-lookup"><span data-stu-id="a820d-107">In addition, Database Engine Tuning Advisor can take XML input, which offers more control over the tuning process.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="a820d-108">O que você aprenderá</span><span class="sxs-lookup"><span data-stu-id="a820d-108">What You Will Learn</span></span>  
 <span data-ttu-id="a820d-109">Este tutorial vai ensiná-lo a navegar na GUI do Orientador de Otimização do Mecanismo de Banco de Dados e executar algumas tarefas básicas com a GUI e o utilitário **dta** .</span><span class="sxs-lookup"><span data-stu-id="a820d-109">This tutorial will teach you how to navigate the Database Engine Tuning Advisor GUI, and how to perform some basic tasks with both the GUI and the **dta** utility.</span></span> <span data-ttu-id="a820d-110">Ele contém as seguintes lições:</span><span class="sxs-lookup"><span data-stu-id="a820d-110">It contains the following lessons:</span></span>  
  
 [<span data-ttu-id="a820d-111">Lição 1: navegação básica no Orientador de Otimização do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="a820d-111">Lesson 1: Basic Navigation in Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
 <span data-ttu-id="a820d-112">Nessa lição, você se acostumará com a nova interface gráfica do usuário do Orientador de Otimização do Mecanismo de Banco de Dados e aprenderá a definir opções de display e layout.</span><span class="sxs-lookup"><span data-stu-id="a820d-112">In this lesson, you will familiarize yourself with the new Database Engine Tuning Advisor GUI and learn how to set display options and layout.</span></span>  
  
 [<span data-ttu-id="a820d-113">Lição 2: Usando o Orientador de Otimização do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="a820d-113">Lesson 2: Using Database Engine Tuning Advisor</span></span>](lesson-2-using-database-engine-tuning-advisor.md)  
 <span data-ttu-id="a820d-114">Nessa lição, você aprenderá a executar tarefas básicas de ajuste com a GUI do Orientador de Otimização do Mecanismo de Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="a820d-114">In this lesson, you will learn how to perform basic tuning tasks with the Database Engine Tuning Advisor GUI.</span></span>  
  
 [<span data-ttu-id="a820d-115">Lição 3: como usar o Utilitário de Prompt de Comando dta</span><span class="sxs-lookup"><span data-stu-id="a820d-115">Lesson 3: Using the dta Command Prompt Utility</span></span>](lesson-3-using-the-dta-command-prompt-utility.md)  
 <span data-ttu-id="a820d-116">Nesta lição, você aprenderá a iniciar o utilitário de prompt de comando **dta** e executar alguns comandos de ajuste simples.</span><span class="sxs-lookup"><span data-stu-id="a820d-116">In this lesson, you learn how to start the **dta** command prompt utility and how to run some simple tuning commands.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a820d-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a820d-117">Requirements</span></span>  
 <span data-ttu-id="a820d-118">Este tutorial destina-se a administradores de banco de dados que não estão familiarizados com a GUI do Orientador de Otimização do Mecanismo de Banco de Dados nem com o utilitário de prompt de comando **dta** , mas que têm experiência com conceitos e estruturas de banco de dados, como índices e exibições indexadas.</span><span class="sxs-lookup"><span data-stu-id="a820d-118">This tutorial is intended for database administrators who are not familiar with the Database Engine Tuning Advisor GUI or the **dta** command prompt utility, but who are experienced with database concepts and structures, such as indexes and indexed views.</span></span>  
  
 <span data-ttu-id="a820d-119">Você deve instalar o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] (ou uma versão posterior) com o banco de dados de exemplo do [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a820d-119">You must install [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] (or a later version) with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="a820d-120">Para reforçar a segurança, os bancos de dados de exemplo não são instalados por padrão.</span><span class="sxs-lookup"><span data-stu-id="a820d-120">To enhance security, the sample databases are not installed by default.</span></span> <span data-ttu-id="a820d-121">Para instalar os bancos de dados de exemplo, consulte [Instalando amostras e bancos de dados de exemplo do SQL Server](http://sqlserversamples.codeplex.com).</span><span class="sxs-lookup"><span data-stu-id="a820d-121">To install the sample databases, see [Installing SQL Server Samples and Sample Databases](http://sqlserversamples.codeplex.com).</span></span>  
  
## <a name="after-you-finish-this-tutorial"></a><span data-ttu-id="a820d-122">Depois de você concluir este tutorial</span><span class="sxs-lookup"><span data-stu-id="a820d-122">After You Finish This Tutorial</span></span>  
 <span data-ttu-id="a820d-123">Depois de você terminar as lições deste tutorial, recorra aos tópicos a seguir para obter mais informações sobre o Orientador de Otimização do Mecanismo de Banco de Dados:</span><span class="sxs-lookup"><span data-stu-id="a820d-123">After you finish the lessons in this tutorial, refer to the following topics for more information about Database Engine Tuning Advisor:</span></span>  
  
-   <span data-ttu-id="a820d-124">[Orientador de Otimização do Mecanismo de Banco de Dados](../../relational-databases/performance/database-engine-tuning-advisor.md) para obter descrições sobre como executar tarefas com essa ferramenta.</span><span class="sxs-lookup"><span data-stu-id="a820d-124">[Database Engine Tuning Advisor](../../relational-databases/performance/database-engine-tuning-advisor.md) for descriptions of how to perform tasks with this tool.</span></span>  
  
-   <span data-ttu-id="a820d-125">[dta Utility](dta-utility.md) para obter material de referência sobre o utilitário de prompt de comando e o arquivo XML opcional que você pode usar para controlar a operação do utilitário.</span><span class="sxs-lookup"><span data-stu-id="a820d-125">[dta Utility](dta-utility.md) for reference material on the command prompt utility and the optional XML file you can use to control the operation of the utility.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="a820d-126">Próxima lição</span><span class="sxs-lookup"><span data-stu-id="a820d-126">Next Lesson</span></span>  
 [<span data-ttu-id="a820d-127">Lição 1: navegação básica no Orientador de Otimização do Mecanismo de Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="a820d-127">Lesson 1: Basic Navigation in Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
