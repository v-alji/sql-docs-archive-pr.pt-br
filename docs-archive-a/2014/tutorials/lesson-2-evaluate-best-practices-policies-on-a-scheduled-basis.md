---
title: 'Lição 2: avaliar as políticas de práticas recomendadas em uma base agendada | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 37ffad63-d6db-4609-8deb-786200659554
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: a454e38ec2f07bf9867183a3894ac4ea001a942e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571727"
---
# <a name="lesson-2-evaluate-best-practices-policies-on-a-scheduled-basis"></a><span data-ttu-id="15294-102">Lição 2: Avaliar políticas de melhores práticas de forma agendada</span><span class="sxs-lookup"><span data-stu-id="15294-102">Lesson 2: Evaluate Best Practices Policies on a Scheduled Basis</span></span>
  <span data-ttu-id="15294-103">Você pode configurar avaliações agendadas de políticas de práticas recomendadas em uma ou mais instâncias do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15294-103">You can configure scheduled evaluations of best practices policies on one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="15294-104">Para configurar políticas de práticas recomendadas para executarem de forma agendada, você deve importar as políticas na instância de destino.</span><span class="sxs-lookup"><span data-stu-id="15294-104">To configure best practices policies to run on a scheduled basis, you must import the policies into the target instance.</span></span>  
  
 <span data-ttu-id="15294-105">Para implantar políticas agendadas em vários servidores, você pode importar as políticas para uma instância, configurar as agendas para cada política, exportar as políticas agendadas para uma pasta e, em seguida, implantar as políticas agendadas em instâncias de destino por meio de Servidores Registrados.</span><span class="sxs-lookup"><span data-stu-id="15294-105">To deploy scheduled policies to multiple servers, you can import the policies to one instance, configure the schedules for each policy, export the scheduled policies to a folder, and then deploy the scheduled policies to target instances through Registered Servers.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="15294-106">As instâncias de destino devem ser executadas no [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] ou em uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="15294-106">The target instances must be running [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] or a later version.</span></span> <span data-ttu-id="15294-107">A automação exige que as políticas sejam armazenadas localmente na instância, o que não tem suporte em versões do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] anteriores ao [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15294-107">Automation requires the policies to be stored locally on the instance, which is not supported by versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that are earlier than [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="15294-108">Nesta lição, você fará o seguinte:</span><span class="sxs-lookup"><span data-stu-id="15294-108">In this lesson, you will do the following:</span></span>  
  
-   <span data-ttu-id="15294-109">Importe as políticas de práticas recomendadas em uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15294-109">Import the best practices policies into an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="15294-110">Configure as políticas para serem executadas em um agendamento.</span><span class="sxs-lookup"><span data-stu-id="15294-110">Configure the policies to run on a schedule.</span></span>  
  
-   <span data-ttu-id="15294-111">Implantar as políticas agendadas de práticas recomendadas em múltiplas instâncias por meio de Servidores Registrados.</span><span class="sxs-lookup"><span data-stu-id="15294-111">Deploy the scheduled best practices policies to multiple instances through Registered Servers.</span></span>  
  
 <span data-ttu-id="15294-112">Eis os tópicos desta lição:</span><span class="sxs-lookup"><span data-stu-id="15294-112">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="15294-113">Importar as políticas para uma única instância</span><span class="sxs-lookup"><span data-stu-id="15294-113">Import the Policies to a Single Instance</span></span>](../../2014/tutorials/import-the-policies-to-a-single-instance.md)  
  
-   [<span data-ttu-id="15294-114">Agendar as políticas</span><span class="sxs-lookup"><span data-stu-id="15294-114">Schedule the Policies</span></span>](../../2014/tutorials/schedule-the-policies.md)  
  
-   [<span data-ttu-id="15294-115">Implantar diretivas agendadas em várias instâncias</span><span class="sxs-lookup"><span data-stu-id="15294-115">Deploy Scheduled Policies to Multiple Instances</span></span>](../../2014/tutorials/deploy-scheduled-policies-to-multiple-instances.md)  
  
## <a name="see-also"></a><span data-ttu-id="15294-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="15294-116">See Also</span></span>  
 [<span data-ttu-id="15294-117">Administrar vários servidores usando servidores de gerenciamento central</span><span class="sxs-lookup"><span data-stu-id="15294-117">Administer Multiple Servers Using Central Management Servers</span></span>](../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
  
