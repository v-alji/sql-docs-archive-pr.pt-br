---
title: Como editar as propriedades de instância CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7a6c719a-3735-43b7-b3ab-dfadd325eca2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b02785a32fa1f64d5da0c3202acd7916da1e65ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678920"
---
# <a name="how-to-edit-the-cdc-instance-properties"></a><span data-ttu-id="90bfe-102">Como editar as propriedades de instância CDC</span><span class="sxs-lookup"><span data-stu-id="90bfe-102">How to Edit the CDC Instance Properties</span></span>
  <span data-ttu-id="90bfe-103">Este procedimento descreve como usar o CDC Designer Console para editar as propriedades de configuração para uma instância CDC.</span><span class="sxs-lookup"><span data-stu-id="90bfe-103">This procedure describes how to use the CDC Designer Console to edit the configuration properties for a CDC instance.</span></span>  
  
### <a name="to-edit-the-cdc-instance-configuration-properties"></a><span data-ttu-id="90bfe-104">Para editar as propriedades de configuração da instância CDC</span><span class="sxs-lookup"><span data-stu-id="90bfe-104">To edit the CDC instance configuration properties</span></span>  
  
1.  <span data-ttu-id="90bfe-105">No menu **Iniciar** , selecione o **CDC Designer Console**.</span><span class="sxs-lookup"><span data-stu-id="90bfe-105">From the **Start** menu, select the **CDC Designer Console**.</span></span>  
  
2.  <span data-ttu-id="90bfe-106">No painel esquerdo, expanda **Change Data Capture** e, em seguida, expanda o serviço que contém a instância com as propriedades que você quer editar.</span><span class="sxs-lookup"><span data-stu-id="90bfe-106">In the left pane, expand **Change Data Capture** then expand the service that contains the instance with the properties that you want to edit.</span></span>  
  
3.  <span data-ttu-id="90bfe-107">Selecione o nome da instância onde você quer editar as propriedades.</span><span class="sxs-lookup"><span data-stu-id="90bfe-107">Select the name of the instance where you want to edit the properties.</span></span>  
  
4.  <span data-ttu-id="90bfe-108">No painel Actions no lado direito do CDC Designer Console, clique em **Properties**.</span><span class="sxs-lookup"><span data-stu-id="90bfe-108">From the Actions pane on the right side of the CDC Designer Console, click **Properties**.</span></span>  
  
     <span data-ttu-id="90bfe-109">Você também pode clicar com o botão direito do mouse na instância em que deseja editar as propriedades e clique em **Properties**.</span><span class="sxs-lookup"><span data-stu-id="90bfe-109">You can also right-click the instance where you want to edit the properties and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="90bfe-110">No editor de Properties, edite as propriedades nas guias a seguir:</span><span class="sxs-lookup"><span data-stu-id="90bfe-110">In the Properties editor, edit the properties in the following tabs:</span></span>  
  
    -   <span data-ttu-id="90bfe-111">**Oracle**: use a guia **Oracle** no editor de Propriedades para fazer alterações na descrição fornecida na página Create CDC database no assistente de Nova Instância e fazer alterações nas informações de conexão de banco de dados de mineração de logs do Oracle.</span><span class="sxs-lookup"><span data-stu-id="90bfe-111">**Oracle**: Use the **Oracle** tab in the Properties editor to make changes to the description you provided in the Create CDC database page in the New Instance wizard and to make changes to the Oracle Log Mining database connection information.</span></span>  
  
         <span data-ttu-id="90bfe-112">Para obter mais informações sobre o que você pode editar nessa guia, consulte [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span><span class="sxs-lookup"><span data-stu-id="90bfe-112">For information about what you can edit in this tab, see [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span></span>  
  
    -   <span data-ttu-id="90bfe-113">**Tables**: use a guia **Tables** para fazer alterações às tabelas e colunas selecionadas do banco de dados de origem Oracle.</span><span class="sxs-lookup"><span data-stu-id="90bfe-113">**Tables**: Use the **Tables** tab to make changes to the tables and columns that you selected from the Oracle source database.</span></span>  
  
         <span data-ttu-id="90bfe-114">Para obter mais informações sobre o que você pode editar nessa guia, consulte Edit [Edit Tables](edit-tables.md).</span><span class="sxs-lookup"><span data-stu-id="90bfe-114">For information about what you can edit in this tab, see Edit [Edit Tables](edit-tables.md)</span></span>  
  
    -   <span data-ttu-id="90bfe-115">**Scripts**: use a guia **Scripts** para executar ou executar novamente um script no banco de dados de origem Oracle que configura o registro em log suplementar.</span><span class="sxs-lookup"><span data-stu-id="90bfe-115">**Scripts**: Use the **Scripts** tab to run or re-run a script on the Oracle source database that will set up supplemental logging.</span></span>  
  
         <span data-ttu-id="90bfe-116">Para obter mais informações sobre o que você pode fazer nessa guia, consulte [Review and Generate Supplemental Logging Scripts](review-and-generate-supplemental-logging-scripts.md).</span><span class="sxs-lookup"><span data-stu-id="90bfe-116">For information about what you can do in this tab, see [Review and Generate Supplemental Logging Scripts](review-and-generate-supplemental-logging-scripts.md).</span></span>  
  
    -   <span data-ttu-id="90bfe-117">**Advanced**: use a guia **Advanced** para acrescentar propriedades especiais à instância de CDC.</span><span class="sxs-lookup"><span data-stu-id="90bfe-117">**Advanced**: Use the **Advanced** tab to add special properties to the CDC instance.</span></span>  
  
         <span data-ttu-id="90bfe-118">Para obter mais informações sobre o que você pode fazer nessa guia, consulte [Edit the Advanced Properties](edit-the-advanced-properties.md).</span><span class="sxs-lookup"><span data-stu-id="90bfe-118">For information about what you can do in this tab, see [Edit the Advanced Properties](edit-the-advanced-properties.md).</span></span>  
  
  
