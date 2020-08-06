---
title: Configurar o Resource Governor usando um modelo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, templates
ms.assetid: f342dec2-d1d6-483e-b44e-98eb7d168b5e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 62edb23cf55a953cb0fef54f002f8eaaa16f58ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582413"
---
# <a name="configure-resource-governor-using-a-template"></a><span data-ttu-id="c768e-102">Configurar o administrador de recursos usando um modelo</span><span class="sxs-lookup"><span data-stu-id="c768e-102">Configure Resource Governor Using a Template</span></span>
  <span data-ttu-id="c768e-103">Você pode configurar o Administrador de recursos usando um modelo que é fornecido em [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c768e-103">You can configure Resource Governor by using a template that is provided in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="c768e-104">**Antes de começar:**  [Permissões](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="c768e-104">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="c768e-105">**Para criar um grupo de carga de trabalho usando:** [um modelo](#ConfRGTemplate)</span><span class="sxs-lookup"><span data-stu-id="c768e-105">**To create a workload group, using:**  [a template](#ConfRGTemplate)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c768e-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c768e-106">Before You Begin</span></span>  
 <span data-ttu-id="c768e-107">Use as etapas a seguir para abrir e modificar um modelo que cria um pool de recursos e um grupo de cargas de trabalho para o pool.</span><span class="sxs-lookup"><span data-stu-id="c768e-107">Use the following steps to open and modify a template that creates a resource pool and a workload group for the pool.</span></span> <span data-ttu-id="c768e-108">Além disso, esse modelo permite que você crie uma função de classificador definida pelo usuário que roteia novas conexões para o grupo padrão ou o grupo de cargas de trabalho que você criar.</span><span class="sxs-lookup"><span data-stu-id="c768e-108">In addition, this template enables you to create a classifier user-defined function that routes new connections to either the default group or the workload group that you create.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c768e-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="c768e-109">Permissions</span></span>  
 <span data-ttu-id="c768e-110">As instruções do [!INCLUDE[tsql](../../includes/tsql-md.md)] do administrador de recursos no modelo exigem a permissão CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="c768e-110">The resource governor [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the template require CONTROL SERVER permission.</span></span>  
  
##  <a name="configure-resource-governor-using-a-template"></a><a name="ConfRGTemplate"></a> <span data-ttu-id="c768e-111">Configurar o administrador de recursos usando um modelo</span><span class="sxs-lookup"><span data-stu-id="c768e-111">Configure Resource Governor Using a Template</span></span>  
 <span data-ttu-id="c768e-112">**Para configurar o Administrador de Recursos usando um modelo no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="c768e-112">**To configure resource governor by using a template in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="c768e-113">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], no menu **Exibir** , clique em **Gerenciador de Modelos**.</span><span class="sxs-lookup"><span data-stu-id="c768e-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="c768e-114">Em **Explorador de Modelos**, expanda **Administrador de Recursos**e clique duas vezes em **Configurar Administrador de Recursos**.</span><span class="sxs-lookup"><span data-stu-id="c768e-114">In **Template Explorer**, expand **Resource Governor**, and then double-click **Configure Resource Governor**.</span></span>  
  
3.  <span data-ttu-id="c768e-115">Em **Conectar ao Database Engine**, digite as informações exigidas e então clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c768e-115">In **Connect to Database Engine**, enter the required information, and then click **OK**.</span></span> <span data-ttu-id="c768e-116">O modelo Configurar administrador de recursos.sql é fornecido no Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="c768e-116">The template Configure Resource Governor.sql is provided in the Query Editor.</span></span> <span data-ttu-id="c768e-117">Use este modelo para criar e configurar um pool de recursos, um grupo de carga de trabalho e uma função de classificador.</span><span class="sxs-lookup"><span data-stu-id="c768e-117">Use this template to create and configure a resource pool, a workload group, and a classifier function.</span></span>  
  
4.  <span data-ttu-id="c768e-118">Para alterar os valores no modelo, pressione CTRL+SHIFT+M.</span><span class="sxs-lookup"><span data-stu-id="c768e-118">To change the values in the template, press CTRL+SHIFT+M.</span></span> <span data-ttu-id="c768e-119">Na janela **Especificar Valores para Parâmetros de Modelos** , digite os valores que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="c768e-119">In the **Specify Values for Template Parameters** window, enter the values that you want to use.</span></span>  
  
5.  <span data-ttu-id="c768e-120">Para salvar as alterações que fizer no modelo, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c768e-120">To save the changes that you make to the template, click **OK**.</span></span>  
  
6.  <span data-ttu-id="c768e-121">Para executar a consulta, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="c768e-121">To run the query, click **Execute**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c768e-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c768e-122">See Also</span></span>  
 <span data-ttu-id="c768e-123">[Administrador de Recursos](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="c768e-123">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="c768e-124">[Habilitar Administrador de Recursos](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="c768e-124">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="c768e-125">[Pool de recursos do Administrador de Recursos](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="c768e-125">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="c768e-126">[Grupos de carga de trabalho do Administrador de Recursos](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="c768e-126">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="c768e-127">[Função de classificação do Administrador de Recursos](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="c768e-127">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="c768e-128">[Exibir Propriedades do Administrador de Recursos](view-resource-governor-properties.md) </span><span class="sxs-lookup"><span data-stu-id="c768e-128">[View Resource Governor Properties](view-resource-governor-properties.md) </span></span>  
 <span data-ttu-id="c768e-129">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c768e-129">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="c768e-130">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c768e-130">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="c768e-131">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c768e-131">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span></span>  
 [<span data-ttu-id="c768e-132">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c768e-132">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
