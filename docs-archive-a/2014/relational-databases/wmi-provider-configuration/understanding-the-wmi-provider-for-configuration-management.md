---
title: Noções básicas sobre o provedor WMI para gerenciamento de configuração | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- WMI Provider for Configuration Management, operations supported
ms.assetid: 92323972-7943-4208-bbf4-050774fb6027
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 0f4f38265093fdb0c27d6bd49ff64ba4b572111e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568364"
---
# <a name="understanding-the-wmi-provider-for-configuration-management"></a><span data-ttu-id="0e6b2-102">Compreendendo o provedor WMI para gerenciamento de configuração</span><span class="sxs-lookup"><span data-stu-id="0e6b2-102">Understanding the WMI Provider for Configuration Management</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="0e6b2-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]fornece o provedor WMI para o gerenciamento de configuração.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides the WMI Provider for Configuration Management.</span></span> <span data-ttu-id="0e6b2-104">Isto permite que você use a WMI (Instrumentação de Gerenciamento do Windows) para gerenciar serviços do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], configurações de rede de cliente e servidor do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e aliases de servidor.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-104">This lets you use Windows Management Instrumentation (WMI) to manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client and server network settings, and server aliases.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="0e6b2-105">os serviços, as configurações de rede e os aliases são representados por objetos WMI no namespace root\Microsoft\SqlServer\ComputerManagement*NN* do computador.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-105">services, network settings, and aliases are represented by WMI objects in the root\Microsoft\SqlServer\ComputerManagement*nn* namespace of the computer.</span></span> <span data-ttu-id="0e6b2-106">Depois que uma conexão for estabelecida com o provedor WMI no computador especificado, os serviços, as configurações de rede e os aliases poderão ser consultados usando WQL ou uma linguagem de script.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-106">After a connection is established with the WMI provider on the specified computer, the services, network settings, and aliases can be queried using WQL or a scripting language.</span></span>  
  
 <span data-ttu-id="0e6b2-107">O Provedor WMI é um provedor de instância.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-107">The WMI Provider is an instance provider.</span></span> <span data-ttu-id="0e6b2-108">Ele fornece instâncias das [classes WMI](../wmi-provider-configuration-classes/wmi-provider-for-configuration-management-classes.md) e oferece suporte às operações assíncronas a seguir.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-108">It supplies instances of the [WMI Classes](../wmi-provider-configuration-classes/wmi-provider-for-configuration-management-classes.md) and supports the following asynchronous operations.</span></span>  
  
 <span data-ttu-id="0e6b2-109">Recuperação de instância</span><span class="sxs-lookup"><span data-stu-id="0e6b2-109">Instance retrieval</span></span>  
 <span data-ttu-id="0e6b2-110">Recuperação de uma instância de tipo de classe específica.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-110">Retrieval of a particular class type instance.</span></span>  
  
 <span data-ttu-id="0e6b2-111">Enumeração</span><span class="sxs-lookup"><span data-stu-id="0e6b2-111">Enumeration</span></span>  
 <span data-ttu-id="0e6b2-112">Enumeração de todas as instâncias de um tipo de classe.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-112">Enumeration of all instances of a class type.</span></span>  
  
 <span data-ttu-id="0e6b2-113">Modification</span><span class="sxs-lookup"><span data-stu-id="0e6b2-113">Modification</span></span>  
 <span data-ttu-id="0e6b2-114">Modificação de uma instância específica de um tipo de classe.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-114">Modification of a particular instance of a class type.</span></span>  
  
 <span data-ttu-id="0e6b2-115">As classes têm métodos que permitem a modificação de suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-115">Classes have methods that allow the modification of their properties.</span></span>  
  
 <span data-ttu-id="0e6b2-116">Exclusão</span><span class="sxs-lookup"><span data-stu-id="0e6b2-116">Deletion</span></span>  
 <span data-ttu-id="0e6b2-117">Remoção de uma instância específica de um tipo de classe.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-117">Removing a particular instance of a class type.</span></span>  
  
 <span data-ttu-id="0e6b2-118">Processamento de consulta</span><span class="sxs-lookup"><span data-stu-id="0e6b2-118">Query processing</span></span>  
 <span data-ttu-id="0e6b2-119">Enumeração de instâncias de um tipo de classe baseado em um filtro.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-119">Enumeration of instances of a class type based on a filter.</span></span>  
  
 <span data-ttu-id="0e6b2-120">Para obter exemplos de aplicativo de gerenciamento usando o provedor WMI para gerenciamento de configuração, consulte [usando WQL e linguagens de script com o provedor WMI para gerenciamento de configuração](using-wql-and-scripting-languages-with-the-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="0e6b2-120">For examples of management application using the WMI Provider for Configuration Management, see [Using WQL and Scripting Languages with the WMI Provider for Configuration Management](using-wql-and-scripting-languages-with-the-wmi-provider.md).</span></span>  
  
 <span data-ttu-id="0e6b2-121">Para obter mais informações sobre como programar aplicativos de gerenciamento usando o provedor WMI, consulte a documentação do WMI no [!INCLUDE[msCoName](../../includes/msconame-md.md)] SDK do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0e6b2-121">For more information about programming management applications using the WMI Provider, see the WMI documentation in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework SDK.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e6b2-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0e6b2-122">See Also</span></span>  
 <span data-ttu-id="0e6b2-123">[Trabalhando com o provedor WMI para gerenciamento de configuração](working-with-the-wmi-provider-for-configuration-management.md) </span><span class="sxs-lookup"><span data-stu-id="0e6b2-123">[Working with the WMI Provider for Configuration Management](working-with-the-wmi-provider-for-configuration-management.md) </span></span>  
 [<span data-ttu-id="0e6b2-124">Usando as linguagens WQL e de scripts com o provedor WMI para gerenciamento de configuração</span><span class="sxs-lookup"><span data-stu-id="0e6b2-124">Using WQL and Scripting Languages with the WMI Provider for Configuration Management</span></span>](using-wql-and-scripting-languages-with-the-wmi-provider.md)  
  
  
