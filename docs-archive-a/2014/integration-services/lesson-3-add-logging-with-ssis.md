---
title: 'Lição 3: adicionando registro em log | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 64cd24cc-ba8e-4bd7-b10b-6b80d8b04af6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 58fcc29759f19ad215a76a1b9ed9bf313b4c869c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573183"
---
# <a name="lesson-3-adding-logging"></a><span data-ttu-id="f1301-102">Lição 3: Como adicionar log</span><span class="sxs-lookup"><span data-stu-id="f1301-102">Lesson 3: Adding Logging</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="f1301-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] inclui recursos de log que permitem solucionar problemas e monitorar a execução do pacote fornecendo um rastreamento de eventos de tarefa e contêiner.</span><span class="sxs-lookup"><span data-stu-id="f1301-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] includes logging features that let you troubleshoot and monitor package execution by providing a trace of task and container events.</span></span> <span data-ttu-id="f1301-104">Os recursos de log são flexíveis, e podem ser habilitados no nível do pacote ou em tarefas individuais e contêineres dentro do pacote.</span><span class="sxs-lookup"><span data-stu-id="f1301-104">The logging features are flexible, and can be enabled at the package level or on individual tasks and containers within the package.</span></span> <span data-ttu-id="f1301-105">Você pode selecionar quais eventos quer você anotar, e criar múltiplos logs vários em um único pacote.</span><span class="sxs-lookup"><span data-stu-id="f1301-105">You can select which events you want to log, and create multiple logs against a single package.</span></span>  
  
 <span data-ttu-id="f1301-106">O log é fornecido por um provedor de log.</span><span class="sxs-lookup"><span data-stu-id="f1301-106">Logging is provided by a log provider.</span></span> <span data-ttu-id="f1301-107">Cada provedor de log pode gravar informações de log em diferentes formatos e tipos de destino.</span><span class="sxs-lookup"><span data-stu-id="f1301-107">Each log provider can write logging information to different formats and destination types.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="f1301-108">fornece os seguintes provedores de log:</span><span class="sxs-lookup"><span data-stu-id="f1301-108">provides the following log providers:</span></span>  
  
-   <span data-ttu-id="f1301-109">Arquivo de texto</span><span class="sxs-lookup"><span data-stu-id="f1301-109">Text file</span></span>  
  
-   [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]  
  
-   <span data-ttu-id="f1301-110">Janela Evento de Log</span><span class="sxs-lookup"><span data-stu-id="f1301-110">Windows Event log</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]  
  
-   <span data-ttu-id="f1301-111">Arquivo XML</span><span class="sxs-lookup"><span data-stu-id="f1301-111">XML file</span></span>  
  
 <span data-ttu-id="f1301-112">Nesta lição, você criará uma cópia do pacote criado na [lição 2: adicionando looping](lesson-2-adding-looping-with-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="f1301-112">In this lesson, you will create a copy of the package that you created in [Lesson 2: Adding Looping](lesson-2-adding-looping-with-ssis.md).</span></span> <span data-ttu-id="f1301-113">Trabalhando com este novo pacote, você irá adicionar e então configurar o log para monitorar eventos específicos durante a execução de pacote.</span><span class="sxs-lookup"><span data-stu-id="f1301-113">Working with this new package, you will then add and configure logging to monitor specific events during package execution.</span></span> <span data-ttu-id="f1301-114">Se você não tiver completado nenhuma das anteriores lições, poderá também copiar o pacote da Lição 2 terminada, que está inclusa no tutorial.</span><span class="sxs-lookup"><span data-stu-id="f1301-114">If you have not completed any of the previous lessons, you can also copy the completed Lesson 2 package that is included with the tutorial.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f1301-115">Este tutorial requer o banco de dados de exemplo **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="f1301-115">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="f1301-116">Para obter mais informações sobre como instalar e implantar o **AdventureWorksDW2012**, [Reporting Services exemplos de produtos no GitHub](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span><span class="sxs-lookup"><span data-stu-id="f1301-116">For more information about how to install and deploy **AdventureWorksDW2012**, [Reporting Services Product Samples on GitHub](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="f1301-117">Tarefas da lição</span><span class="sxs-lookup"><span data-stu-id="f1301-117">Lesson Tasks</span></span>  
 <span data-ttu-id="f1301-118">Esta lição contém as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="f1301-118">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="f1301-119">Etapa 1: Copiar o pacote da Lição 2</span><span class="sxs-lookup"><span data-stu-id="f1301-119">Step 1: Copying the Lesson 2 Package</span></span>](lesson-3-1-copying-the-lesson-2-package.md)  
  
-   [<span data-ttu-id="f1301-120">Etapa 2: Adicionar e configurar registro em log</span><span class="sxs-lookup"><span data-stu-id="f1301-120">Step 2: Adding and Configuring Logging</span></span>](lesson-3-2-adding-and-configuring-logging.md)  
  
-   [<span data-ttu-id="f1301-121">Etapa 3: Testar o pacote de tutorial da Lição 3</span><span class="sxs-lookup"><span data-stu-id="f1301-121">Step 3: Testing the Lesson 3 Tutorial Package</span></span>](../integration-services/lesson-3-3-testing-the-lesson-3-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="f1301-122">Iniciar a lição</span><span class="sxs-lookup"><span data-stu-id="f1301-122">Start the Lesson</span></span>  
 [<span data-ttu-id="f1301-123">Etapa 1: Copiar o pacote da Lição 2</span><span class="sxs-lookup"><span data-stu-id="f1301-123">Step 1: Copying the Lesson 2 Package</span></span>](lesson-3-1-copying-the-lesson-2-package.md)  
  
  
