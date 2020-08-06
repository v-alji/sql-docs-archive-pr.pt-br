---
title: Configurar valores de limite para limpeza e correspondência | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.admin.config.general.f1
helpviewer_keywords:
- cleansing,threshold value
- cleansing threshold values
- matching,threshold value
ms.assetid: d2305409-7115-45a4-8f60-1213c0a47368
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0faf64e96468a3a9aac0de12d3ec3acbb1e1ed85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678977"
---
# <a name="configure-threshold-values-for-cleansing-and-matching"></a><span data-ttu-id="834a1-102">Configurar valores de limite para limpeza e correspondência</span><span class="sxs-lookup"><span data-stu-id="834a1-102">Configure Threshold Values for Cleansing and Matching</span></span>
  <span data-ttu-id="834a1-103">Este tópico descreve como configurar valores de limite que serão usados durante a limpeza auxiliada por computador e as atividades correspondentes no [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="834a1-103">This topic describes how to configure threshold values that will be used during the computer-assisted cleansing and matching activities in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="834a1-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="834a1-104">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="834a1-105">Segurança</span><span class="sxs-lookup"><span data-stu-id="834a1-105">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="834a1-106">Permissões</span><span class="sxs-lookup"><span data-stu-id="834a1-106">Permissions</span></span>  
 <span data-ttu-id="834a1-107">É necessário ter a função dqs_administrator no banco de dados DQS_MAIN para configurar esses valores de limite.</span><span class="sxs-lookup"><span data-stu-id="834a1-107">You must have the dqs_administrator role on the DQS_MAIN database to configure these threshold values.</span></span>  
  
##  <a name="configuring-the-threshold-values"></a><a name="Configure"></a> <span data-ttu-id="834a1-108">Configurando os valores de limite</span><span class="sxs-lookup"><span data-stu-id="834a1-108">Configuring the Threshold Values</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="834a1-109">[Execute o aplicativo Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="834a1-109">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="834a1-110">Na tela inicial do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , clique em **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="834a1-110">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="834a1-111">Em seguida, clique na guia **configurações gerais** . Esta guia permite que você especifique valores de limite para limpeza, bem como atividades correspondentes.</span><span class="sxs-lookup"><span data-stu-id="834a1-111">Next, click the **General Settings** tab. This tab enables you to specify threshold values for cleansing as well as matching activities.</span></span>  
  
4.  <span data-ttu-id="834a1-112">Para especificar valores de limote para a atividade de limpeza, especifique os valores apropriados nas seguintes caixas na área **Limpeza Interativa** :</span><span class="sxs-lookup"><span data-stu-id="834a1-112">To specify threshold values for the cleansing activity, specify appropriate values in the following boxes under the **Interactive Cleansing** area:</span></span>  
  
    -   <span data-ttu-id="834a1-113">**Pontuação mínima para sugestões**: a pontuação mínima ou o nível de confiança que será usado pelo DQS para sugerir substitutos para um valor durante o processo de limpeza auxiliada por computador.</span><span class="sxs-lookup"><span data-stu-id="834a1-113">**Min score for suggestions**: The minimum score or the confidence level that will be used by DQS for suggesting replacements for a value during the computer-assisted cleansing process.</span></span> <span data-ttu-id="834a1-114">Insira um valor na notação decimal do valor percentual correspondente.</span><span class="sxs-lookup"><span data-stu-id="834a1-114">Enter a value in the decimal notation of the corresponding percentage value.</span></span> <span data-ttu-id="834a1-115">Por exemplo, digite 0,75 para 75%.</span><span class="sxs-lookup"><span data-stu-id="834a1-115">For example, type 0.75 for 75%.</span></span> <span data-ttu-id="834a1-116">Esse valor deve ser inferior ou igual ao valor especificado na caixa **Pontuação mínima para correções automáticas** .</span><span class="sxs-lookup"><span data-stu-id="834a1-116">This value should be less than or equal to the value specified in the **Min score for auto corrections** box.</span></span> <span data-ttu-id="834a1-117">O valor padrão é 0,7.</span><span class="sxs-lookup"><span data-stu-id="834a1-117">The default value is 0.7.</span></span>  
  
    -   <span data-ttu-id="834a1-118">**Pontuação mínima para correções automáticas**: a pontuação mínima ou o nível de confiança que será usado pelo DQS para corrigir automaticamente um valor durante o processo de limpeza auxiliada por computador.</span><span class="sxs-lookup"><span data-stu-id="834a1-118">**Min score for auto corrections**: The minimum score or the confidence level that will be used by DQS for automatically correcting a value during the computer-assisted cleansing process.</span></span> <span data-ttu-id="834a1-119">Insira um valor na notação decimal do valor percentual correspondente.</span><span class="sxs-lookup"><span data-stu-id="834a1-119">Enter a value in the decimal notation of the corresponding percentage value.</span></span> <span data-ttu-id="834a1-120">Por exemplo, insira 0,9 para 90%.</span><span class="sxs-lookup"><span data-stu-id="834a1-120">For example, enter 0.9 for 90%.</span></span> <span data-ttu-id="834a1-121">O valor padrão é 0,8.</span><span class="sxs-lookup"><span data-stu-id="834a1-121">The default value is 0.8.</span></span>  
  
5.  <span data-ttu-id="834a1-122">Para especificar um valor de limite para a atividade de correspondência, especifique um valor na caixa **Pontuação mínima de registro** na área **Correspondência** .</span><span class="sxs-lookup"><span data-stu-id="834a1-122">To specify threshold value for the matching activity, specify a value in the **Min record score** box under the **Matching** area.</span></span> <span data-ttu-id="834a1-123">Esse valor significa a pontuação mínima para um registro a ser considerado como uma correspondência para outro registro.</span><span class="sxs-lookup"><span data-stu-id="834a1-123">This value signifies the minimum score for a record to be considered as a match for another record.</span></span> <span data-ttu-id="834a1-124">O valor padrão é 80%.</span><span class="sxs-lookup"><span data-stu-id="834a1-124">The default value is 80%.</span></span>  
  
6.  <span data-ttu-id="834a1-125">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="834a1-125">Click **Close**.</span></span>  
  
  
