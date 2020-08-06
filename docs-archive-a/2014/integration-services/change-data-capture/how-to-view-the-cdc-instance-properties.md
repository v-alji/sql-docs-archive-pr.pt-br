---
title: Como exibir as propriedades de instância CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4bce9b82-7bbd-41df-b3f4-4b40b8bad474
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 86fa298b0e02a16ddbaea220ef7f3d9f6172bf85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681056"
---
# <a name="how-to-view-the-cdc-instance-properties"></a><span data-ttu-id="dda5b-102">Como exibir as propriedades de instância CDC</span><span class="sxs-lookup"><span data-stu-id="dda5b-102">How to View the CDC Instance Properties</span></span>
  <span data-ttu-id="dda5b-103">Este procedimento descreve como usar o CDC Designer Console para exibir informações sobre as instâncias que você cria para ajudar a gerenciar a operação das instâncias.</span><span class="sxs-lookup"><span data-stu-id="dda5b-103">This procedure describes how to use the CDC Designer Console to view information about the instances that you create to help manage the operation of the instances.</span></span>  
  
### <a name="to-view-information-about-a-specific-instance"></a><span data-ttu-id="dda5b-104">Para exibir informações sobre uma instância específica</span><span class="sxs-lookup"><span data-stu-id="dda5b-104">To view information about a specific instance</span></span>  
  
1.  <span data-ttu-id="dda5b-105">No menu **Iniciar** , selecione o **CDC Designer Console**.</span><span class="sxs-lookup"><span data-stu-id="dda5b-105">From the **Start** menu, select the **CDC Designer Console**.</span></span>  
  
2.  <span data-ttu-id="dda5b-106">No painel esquerdo, expanda **Change Data Capture** e, em seguida, expanda o serviço que contém a instância que você quer exibir.</span><span class="sxs-lookup"><span data-stu-id="dda5b-106">In the left pane, expand **Change Data Capture** then expand the service that contains the instance you want to view.</span></span>  
  
3.  <span data-ttu-id="dda5b-107">Selecione o nome de uma instância com a qual você quer trabalhar.</span><span class="sxs-lookup"><span data-stu-id="dda5b-107">Select the name of an instance you want to work with.</span></span>  
  
     <span data-ttu-id="dda5b-108">As informações sobre a instância são exibidas na parte central do CDC Designer Console.</span><span class="sxs-lookup"><span data-stu-id="dda5b-108">The information about the instance is displayed in the center part of the CDC Designer Console.</span></span> <span data-ttu-id="dda5b-109">Elas são divididas em quatro guias.</span><span class="sxs-lookup"><span data-stu-id="dda5b-109">It is divided into four tabs.</span></span> <span data-ttu-id="dda5b-110">Todas as guias são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="dda5b-110">All of the tabs are read only.</span></span>  
  
     <span data-ttu-id="dda5b-111">**Status**</span><span class="sxs-lookup"><span data-stu-id="dda5b-111">**Status**</span></span>  
     <span data-ttu-id="dda5b-112">Esta guia exibe as informações sobre o status atual da captura de dados de alterações para a instância.</span><span class="sxs-lookup"><span data-stu-id="dda5b-112">This tab displays the information about the current status of the change data capture for the instance.</span></span> <span data-ttu-id="dda5b-113">Para obter informações sobre o que é exibido nesta guia, consulte a seção **Guias do visualizador** em [Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="dda5b-113">For information about what is displayed in this tab, see the **Viewer Tabs** section in [Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
     <span data-ttu-id="dda5b-114">**Oracle**</span><span class="sxs-lookup"><span data-stu-id="dda5b-114">**Oracle**</span></span>  
     <span data-ttu-id="dda5b-115">Esta guia exibe informações gerais sobre a instância CDC e o banco de dados de origem Oracle.</span><span class="sxs-lookup"><span data-stu-id="dda5b-115">This tab displays general information about the CDC instance and the Oracle source database.</span></span> <span data-ttu-id="dda5b-116">Para obter mais informações sobre o que é exibido nessa guia, consulte [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span><span class="sxs-lookup"><span data-stu-id="dda5b-116">For information about what is displayed in this tab, see [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span></span>  
  
     <span data-ttu-id="dda5b-117">**Tabelas**</span><span class="sxs-lookup"><span data-stu-id="dda5b-117">**Tables**</span></span>  
     <span data-ttu-id="dda5b-118">Esta guia exibe as informações sobre as tabelas incluídas na captura de dados de alterações.</span><span class="sxs-lookup"><span data-stu-id="dda5b-118">This tab displays information about the tables included in the change data capture.</span></span> <span data-ttu-id="dda5b-119">Ela também lista as colunas que são capturadas.</span><span class="sxs-lookup"><span data-stu-id="dda5b-119">It also lists the columns that are captured.</span></span> <span data-ttu-id="dda5b-120">Para obter mais informações sobre o que é exibido nessa guia, consulte [Edit Tables](edit-tables.md).</span><span class="sxs-lookup"><span data-stu-id="dda5b-120">For information about what is displayed in this tab, see [Edit Tables](edit-tables.md).</span></span>  
  
     <span data-ttu-id="dda5b-121">**Avançado**</span><span class="sxs-lookup"><span data-stu-id="dda5b-121">**Advanced**</span></span>  
     <span data-ttu-id="dda5b-122">Esta guia exibe uma lista de propriedades avançadas que você define no editor de propriedades.</span><span class="sxs-lookup"><span data-stu-id="dda5b-122">This tab displays a list of advanced properties that you define in the properties editor.</span></span> <span data-ttu-id="dda5b-123">Para obter mais informações sobre o que é exibido nessa guia, consulte [Edit the Advanced Properties](edit-the-advanced-properties.md).</span><span class="sxs-lookup"><span data-stu-id="dda5b-123">For information about what is displayed in this tab, see [Edit the Advanced Properties](edit-the-advanced-properties.md).</span></span>  
  
  
