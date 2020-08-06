---
title: Criar um projeto de qualidade de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.dqproject.newdqproject.f1
helpviewer_keywords:
- create,data quality project
- data quality project,create
ms.assetid: 19c52d2b-d28e-4449-ab59-5fe0dc326cd9
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3bab14b34123464450bcf0de7540364fc642343e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678969"
---
# <a name="create-a-data-quality-project"></a><span data-ttu-id="2c262-102">Criar um projeto de qualidade de dados</span><span class="sxs-lookup"><span data-stu-id="2c262-102">Create a Data Quality Project</span></span>
  <span data-ttu-id="2c262-103">Este tópico descreve como criar um projeto de qualidade de dados usando o [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c262-103">This topic describes how to create a data quality project by using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span> <span data-ttu-id="2c262-104">Um projeto de qualidade de dados é usado para executar a atividade de limpeza ou correspondência no [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="2c262-104">A data quality project is used to run the cleansing or matching activity in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2c262-105">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="2c262-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="2c262-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2c262-106">Prerequisites</span></span>  
 <span data-ttu-id="2c262-107">Você deve ter uma base de dados de conhecimento relevante para usar no projeto de qualidade de dados para a atividade de limpeza ou correspondência.</span><span class="sxs-lookup"><span data-stu-id="2c262-107">You must have a relevant knowledge base to use in the data quality project for the cleansing or matching activity.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2c262-108">Segurança</span><span class="sxs-lookup"><span data-stu-id="2c262-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2c262-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="2c262-109">Permissions</span></span>  
 <span data-ttu-id="2c262-110">Você deve ter a função dqs_kb_editor ou dqs_kb_operator no banco de dados DQS_MAIN para criar um projeto de qualidade de dados.</span><span class="sxs-lookup"><span data-stu-id="2c262-110">You must have the dqs_kb_editor or dqs_kb_operator role on the DQS_MAIN database to create a data quality project.</span></span>  
  
##  <a name="create-a-data-quality-project"></a><a name="Create"></a><span data-ttu-id="2c262-111">Criar um projeto de qualidade de dados</span><span class="sxs-lookup"><span data-stu-id="2c262-111">Create a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="2c262-112">[Execute o aplicativo Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="2c262-112">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="2c262-113">Na tela inicial do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , clique em **Novo projeto de qualidade de dados**.</span><span class="sxs-lookup"><span data-stu-id="2c262-113">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **New data quality project**.</span></span>  
  
3.  <span data-ttu-id="2c262-114">Na tela **Novo Projeto de Qualidade de Dados** :</span><span class="sxs-lookup"><span data-stu-id="2c262-114">In the **New Data Quality Project** screen:</span></span>  
  
    1.  <span data-ttu-id="2c262-115">Na caixa **Nome** , digite um nome para o novo projeto de qualidade de dados.</span><span class="sxs-lookup"><span data-stu-id="2c262-115">In the **Name** box, type a name for the new data quality project.</span></span>  
  
    2.  <span data-ttu-id="2c262-116">(Opcional) Na caixa **Descrição** , digite uma descrição para o novo projeto de qualidade de dados.</span><span class="sxs-lookup"><span data-stu-id="2c262-116">(Optional) In the **Description** box, type a description for the new data quality project.</span></span>  
  
    3.  <span data-ttu-id="2c262-117">Na lista **Usar base de dados de conhecimento** , clique para selecionar uma base de dados de conhecimento a ser usada no projeto de qualidade de dados.</span><span class="sxs-lookup"><span data-stu-id="2c262-117">In the **Use Knowledge base** list, click to select a knowledge base to be used for the data quality project.</span></span> <span data-ttu-id="2c262-118">A área **Detalhes da base de dados de conhecimento: <Knowledge_Base_Name>** do lado direito exibe os nomes de domínio disponíveis na base de dados de conhecimento selecionada.</span><span class="sxs-lookup"><span data-stu-id="2c262-118">The **Knowledge base details: <Knowledge_Base_Name>** area on the right side displays the domain names available in the selected knowledge base.</span></span>  
  
    4.  <span data-ttu-id="2c262-119">Na área **Selecionar Atividade** , clique em uma atividade que você deseja executar usando este projeto de qualidade de dados:</span><span class="sxs-lookup"><span data-stu-id="2c262-119">In the **Select Activity** area, click on an activity that you want to perform using this data quality project:</span></span>  
  
        -   <span data-ttu-id="2c262-120">**Limpeza**: selecione esta atividade para limpar os dados de origem.</span><span class="sxs-lookup"><span data-stu-id="2c262-120">**Cleansing**: Select this activity to cleanse the source data.</span></span>  
  
        -   <span data-ttu-id="2c262-121">**Correspondência**: selecione esta atividade para fazer a correspondência.</span><span class="sxs-lookup"><span data-stu-id="2c262-121">**Matching**: Select this activity to perform matching.</span></span> <span data-ttu-id="2c262-122">Esta atividade só estará disponível se a base de dados de conhecimento selecionada para o projeto de qualidade de dados contiver uma política de correspondência.</span><span class="sxs-lookup"><span data-stu-id="2c262-122">This activity is available only if the knowledge base selected for the data quality project contains a matching policy.</span></span>  
  
4.  <span data-ttu-id="2c262-123">Clique em **Criar** para criar um projeto de qualidade de dados.</span><span class="sxs-lookup"><span data-stu-id="2c262-123">Click **Create** to create a data quality project.</span></span>  
  
##  <a name="follow-up-after-creating-a-data-quality-project"></a><a name="FollowUp"></a><span data-ttu-id="2c262-124">Acompanhamento: depois de criar um projeto de qualidade de dados</span><span class="sxs-lookup"><span data-stu-id="2c262-124">Follow Up: After Creating a Data Quality Project</span></span>  
 <span data-ttu-id="2c262-125">Depois que você criar um projeto de qualidade de dados, verá um assistente que deverá ser usado para executar a atividade selecionada: limpeza ou correspondência.</span><span class="sxs-lookup"><span data-stu-id="2c262-125">After you create a data quality project, you are presented with a wizard that you use to perform the selected activity: cleansing or matching.</span></span> <span data-ttu-id="2c262-126">Para obter mais informações sobre a limpeza e correspondência de atividades, consulte [Limpeza de dados](../../2014/data-quality-services/data-cleansing.md) e [Correspondência de dados](../../2014/data-quality-services/data-matching.md).</span><span class="sxs-lookup"><span data-stu-id="2c262-126">For more information about the cleansing and matching activities, see [Data Cleansing](../../2014/data-quality-services/data-cleansing.md) and [Data Matching](../../2014/data-quality-services/data-matching.md).</span></span>  
  
  
