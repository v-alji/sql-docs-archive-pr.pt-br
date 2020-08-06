---
title: Propriedades do trabalho e novo trabalho (página Geral) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.general.f1
ms.assetid: b6832840-1c18-4db8-94fc-080db880ae9f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7a5d2ab84ed211a03a3c217bd5f4cd54453a4dc5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680281"
---
# <a name="job-properties-and-new-job-general-page"></a><span data-ttu-id="e78e1-102">Propriedades do trabalho e novo trabalho (página Geral)</span><span class="sxs-lookup"><span data-stu-id="e78e1-102">Job Properties and New Job (General Page)</span></span>
  <span data-ttu-id="e78e1-103">Use esta página para exibir e modificar as propriedades gerais de um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trabalho do Agent.</span><span class="sxs-lookup"><span data-stu-id="e78e1-103">Use this page to view and modify the general properties of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e78e1-104">Opções</span><span class="sxs-lookup"><span data-stu-id="e78e1-104">Options</span></span>  
 <span data-ttu-id="e78e1-105">**Nome**</span><span class="sxs-lookup"><span data-stu-id="e78e1-105">**Name**</span></span>  
 <span data-ttu-id="e78e1-106">Altera o nome do trabalho.</span><span class="sxs-lookup"><span data-stu-id="e78e1-106">Change the name of the job.</span></span>  
  
 <span data-ttu-id="e78e1-107">**Proprietário**</span><span class="sxs-lookup"><span data-stu-id="e78e1-107">**Owner**</span></span>  
 <span data-ttu-id="e78e1-108">Seleciona o proprietário para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="e78e1-108">Select the owner for the job.</span></span>  
  
 <span data-ttu-id="e78e1-109">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="e78e1-109">**Category**</span></span>  
 <span data-ttu-id="e78e1-110">Seleciona a categoria de trabalho para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="e78e1-110">Select the job category for the job.</span></span>  
  
 <span data-ttu-id="e78e1-111">**...**</span><span class="sxs-lookup"><span data-stu-id="e78e1-111">**...**</span></span>  
 <span data-ttu-id="e78e1-112">Exibe os trabalhos na categoria selecionada.</span><span class="sxs-lookup"><span data-stu-id="e78e1-112">View the jobs in the selected category.</span></span>  
  
 <span data-ttu-id="e78e1-113">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="e78e1-113">**Description**</span></span>  
 <span data-ttu-id="e78e1-114">Altera a descrição do trabalho.</span><span class="sxs-lookup"><span data-stu-id="e78e1-114">Change the description of the job.</span></span>  
  
 <span data-ttu-id="e78e1-115">**Habilitado**</span><span class="sxs-lookup"><span data-stu-id="e78e1-115">**Enabled**</span></span>  
 <span data-ttu-id="e78e1-116">Habilita o trabalho.</span><span class="sxs-lookup"><span data-stu-id="e78e1-116">Enable the job.</span></span> <span data-ttu-id="e78e1-117">Quando o trabalho não está habilitado, ele não é executado em resposta a uma agenda ou a um alerta, embora você ainda possa iniciar o trabalho usando o procedimento armazenado **sp_start_job** .</span><span class="sxs-lookup"><span data-stu-id="e78e1-117">When the job is not enabled, the job does not run in response to a schedule or an alert, although you can still start the job using the **sp_start_job** stored procedure.</span></span>  
  
 <span data-ttu-id="e78e1-118">**Origem**</span><span class="sxs-lookup"><span data-stu-id="e78e1-118">**Source**</span></span>  
 <span data-ttu-id="e78e1-119">Exibe o servidor mestre para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="e78e1-119">Displays the master server for the job.</span></span> <span data-ttu-id="e78e1-120">Só disponível na página **Propriedades do Trabalho** – Geral.</span><span class="sxs-lookup"><span data-stu-id="e78e1-120">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="e78e1-121">**Criado**</span><span class="sxs-lookup"><span data-stu-id="e78e1-121">**Created**</span></span>  
 <span data-ttu-id="e78e1-122">Exibe a data e hora em que o trabalho foi criado.</span><span class="sxs-lookup"><span data-stu-id="e78e1-122">Displays the date and time that the job was created.</span></span> <span data-ttu-id="e78e1-123">Só disponível na página **Propriedades do Trabalho** – Geral.</span><span class="sxs-lookup"><span data-stu-id="e78e1-123">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="e78e1-124">**Última modificação**</span><span class="sxs-lookup"><span data-stu-id="e78e1-124">**Last modified**</span></span>  
 <span data-ttu-id="e78e1-125">Exibe a data e a hora em que o trabalho foi modificado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="e78e1-125">Displays the date and time that the job was last modified.</span></span> <span data-ttu-id="e78e1-126">Só disponível na página **Propriedades do Trabalho** – Geral.</span><span class="sxs-lookup"><span data-stu-id="e78e1-126">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="e78e1-127">**Última execução**</span><span class="sxs-lookup"><span data-stu-id="e78e1-127">**Last executed**</span></span>  
 <span data-ttu-id="e78e1-128">Exibe a data e hora em que a execução do trabalho foi iniciada pela última vez.</span><span class="sxs-lookup"><span data-stu-id="e78e1-128">Displays the date and time that the job last started running.</span></span> <span data-ttu-id="e78e1-129">Só disponível na página **Propriedades do Trabalho** – Geral.</span><span class="sxs-lookup"><span data-stu-id="e78e1-129">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="e78e1-130">**Exibir Histórico de Trabalho**</span><span class="sxs-lookup"><span data-stu-id="e78e1-130">**View Job History**</span></span>  
 <span data-ttu-id="e78e1-131">Exibe o histórico do trabalho para o trabalho</span><span class="sxs-lookup"><span data-stu-id="e78e1-131">View the job history for the job.</span></span> <span data-ttu-id="e78e1-132">Só disponível na página **Propriedades do Trabalho** – Geral.</span><span class="sxs-lookup"><span data-stu-id="e78e1-132">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e78e1-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e78e1-133">See Also</span></span>  
 <span data-ttu-id="e78e1-134">[Implementar trabalhos](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="e78e1-134">[Implement Jobs](implement-jobs.md) </span></span>  
 [<span data-ttu-id="e78e1-135">Categorias de trabalho: Gerenciar categorias de trabalho</span><span class="sxs-lookup"><span data-stu-id="e78e1-135">Job Categories: Manage Job Categories</span></span>](job-categories-manage-job-categories.md)  
  
  
