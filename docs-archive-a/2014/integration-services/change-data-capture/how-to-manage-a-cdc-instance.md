---
title: Como gerenciar uma instância CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5d9e677f-b872-497d-9cde-472184a214ab
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e387b9e1a75b7279a68d1c9c9b637f5473071013
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678919"
---
# <a name="how-to-manage-a-cdc-instance"></a><span data-ttu-id="7c990-102">How to Manage a CDC Instance</span><span class="sxs-lookup"><span data-stu-id="7c990-102">How to Manage a CDC Instance</span></span>
  <span data-ttu-id="7c990-103">Este procedimento descreve como usar o CDC Designer Console para gerenciar operações de instância CDC em runtime.</span><span class="sxs-lookup"><span data-stu-id="7c990-103">This procedure describes how to use the CDC Designer Console to manage CDC instance operations at runtime.</span></span>  
  
### <a name="to-manage-cdc-instance-operations"></a><span data-ttu-id="7c990-104">Para gerenciar operações de instância CDC</span><span class="sxs-lookup"><span data-stu-id="7c990-104">To manage CDC instance operations</span></span>  
  
1.  <span data-ttu-id="7c990-105">No menu **Iniciar** , selecione o **CDC Designer Console**.</span><span class="sxs-lookup"><span data-stu-id="7c990-105">From the **Start** menu, select the **CDC Designer Console**.</span></span>  
  
2.  <span data-ttu-id="7c990-106">No painel esquerdo, expanda **Change Data Capture** e, em seguida, expanda o serviço que contém a instância que você quer exibir.</span><span class="sxs-lookup"><span data-stu-id="7c990-106">In the left pane, expand **Change Data Capture** then expand the service that contains the instance you want to view.</span></span>  
  
3.  <span data-ttu-id="7c990-107">Selecione o nome de uma instância com a qual você quer trabalhar.</span><span class="sxs-lookup"><span data-stu-id="7c990-107">Select the name of an instance you want to work with.</span></span>  
  
4.  <span data-ttu-id="7c990-108">No painel **Ações** do lado direito do CDC Designer Console, clique na operação que você quer realizar.</span><span class="sxs-lookup"><span data-stu-id="7c990-108">From the **Actions** pane on the right side of the CDC Designer Console, click on the operation you want to carry out.</span></span>  
  
     <span data-ttu-id="7c990-109">Você também pode clicar com o botão direito no nome da instância no painel esquerdo e selecionar a operação que deseja realizar.</span><span class="sxs-lookup"><span data-stu-id="7c990-109">You can also right-click the name of the instance in the left pane and select the operation you want to carry out.</span></span>  
  
     <span data-ttu-id="7c990-110">Você pode realizar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="7c990-110">You can carry out the following tasks:</span></span>  
  
    -   <span data-ttu-id="7c990-111">**Iniciar**: iniciar a captura de alterações.</span><span class="sxs-lookup"><span data-stu-id="7c990-111">**Start**: To start capturing changes.</span></span>  
  
    -   <span data-ttu-id="7c990-112">**Parar**: parar a captura de alterações</span><span class="sxs-lookup"><span data-stu-id="7c990-112">**Stop**: To stop capturing changes</span></span>  
  
    -   <span data-ttu-id="7c990-113">**Redefinir**: clique em **Redefinir** para reiniciar a instância CDC a seu estado inicial (vazio).</span><span class="sxs-lookup"><span data-stu-id="7c990-113">**Reset**: Click **Reset** to reset the CDC instance to its initial (empty) state.</span></span> <span data-ttu-id="7c990-114">Esta opção está disponível quando a instância CDC é parada.</span><span class="sxs-lookup"><span data-stu-id="7c990-114">This option is available when the CDC instance is stopped.</span></span> <span data-ttu-id="7c990-115">Todas as alterações nas tabelas de alteração e o estado interno da instância CDC são excluídos.</span><span class="sxs-lookup"><span data-stu-id="7c990-115">All changes in the change tables and the CDC instance internal state are deleted.</span></span> <span data-ttu-id="7c990-116">Quando a instância CDC é iniciada posteriormente, a captura de alterações inicia a partir desse ponto no tempo e só inclui transações iniciadas depois que a instância CDC iniciou.</span><span class="sxs-lookup"><span data-stu-id="7c990-116">When the CDC instance is started later on, change capture will start from that point in time and only includes transactions that started after the CDC instance started.</span></span>  
  
    -   <span data-ttu-id="7c990-117">**Excluir**: excluir a instância CDC.</span><span class="sxs-lookup"><span data-stu-id="7c990-117">**Delete**: To delete the CDC instance.</span></span>  
  
    -   <span data-ttu-id="7c990-118">**Oracle Logging Script**: clique em **Oracle Logging Script** para exibir a caixa de diálogo do script de registro em log do Oracle com o script de registro em log suplementar do Oracle.</span><span class="sxs-lookup"><span data-stu-id="7c990-118">**Oracle Logging Script**: Click **Oracle Logging Script** to display the Oracle Logging script dialog box with the Oracle supplemental-logging script.</span></span> <span data-ttu-id="7c990-119">Para obter informações sobre o que você pode fazer nesta caixa de diálogo, consulte [Oracle Supplemental Logging Script](oracle-supplemental-logging-script.md).</span><span class="sxs-lookup"><span data-stu-id="7c990-119">For information on what you can do in this dialog box, see [Oracle Supplemental Logging Script](oracle-supplemental-logging-script.md).</span></span>  
  
         <span data-ttu-id="7c990-120">**Observação**: quando você executa os scripts de log suplementares, a caixa de diálogo Oracle Credentials for Running Script abre e você fornece um nome de usuário e senha do Oracle válidos.</span><span class="sxs-lookup"><span data-stu-id="7c990-120">**Note**: When you run the supplemental logging scripts, the Oracle Credentials for Running Script dialog box opens where you provide a valid Oracle user name and password.</span></span> <span data-ttu-id="7c990-121">Para obter informações sobre como fornecer as credenciais corretas do Oracle, consulte [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span><span class="sxs-lookup"><span data-stu-id="7c990-121">For information on how to provide the proper Oracle credentials, see [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span></span>  
  
    -   <span data-ttu-id="7c990-122">**CDC Instance Deployment**: gerar um script de implantação para a Instância CDC.</span><span class="sxs-lookup"><span data-stu-id="7c990-122">**CDC Instance Deployment**: To generate a deployment script for the CDC Instance.</span></span> <span data-ttu-id="7c990-123">Para obter informações sobre essa caixa de diálogo, consulte [CDC Instance Deployment Script](cdc-instance-deployment-script.md).</span><span class="sxs-lookup"><span data-stu-id="7c990-123">For information about this dialog box, see [CDC Instance Deployment Script](cdc-instance-deployment-script.md).</span></span>  
  
     <span data-ttu-id="7c990-124">Para obter mais informações sobre estas tarefas, consulte [Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="7c990-124">For more information about these tasks, see [Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
 <span data-ttu-id="7c990-125">Você também pode selecionar **Propriedades** para editar as propriedades de configuração da instância CDC.</span><span class="sxs-lookup"><span data-stu-id="7c990-125">You can also select **Properties** to edit the CDC instance configuration properties.</span></span> <span data-ttu-id="7c990-126">Para obter mais informações sobre as propriedades da instância CDC, consulte [Edit Instance Properties](edit-instance-properties.md).</span><span class="sxs-lookup"><span data-stu-id="7c990-126">For more information about editing the CDC instance properties, see [Edit Instance Properties](edit-instance-properties.md).</span></span>  
  
  
