---
title: Propriedades do assinante| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configdistwizard.subscribers.f1
helpviewer_keywords:
- Subscriber Properties dialog box
ms.assetid: 32aa0347-64e4-4aa4-ac57-6bd3e5d52070
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 81ab9cf5f277ccfe1044e5a7083f019db9d843ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685048"
---
# <a name="subscriber-properties"></a><span data-ttu-id="55d8b-102">Propriedades do Assinante</span><span class="sxs-lookup"><span data-stu-id="55d8b-102">Subscriber Properties</span></span>
  <span data-ttu-id="55d8b-103">A caixa de diálogo **Propriedades do Assinante** contém informações relevantes para os Assinantes que executam versões do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anteriores a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55d8b-103">The **Subscriber Properties** dialog box contains information relevant to Subscribers running versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="55d8b-104">Opções</span><span class="sxs-lookup"><span data-stu-id="55d8b-104">Options</span></span>  
 <span data-ttu-id="55d8b-105">**Conexão do Agente com o Assinante**</span><span class="sxs-lookup"><span data-stu-id="55d8b-105">**Agent Connection to the Subscriber**</span></span>  
 <span data-ttu-id="55d8b-106">O contexto no qual o Agente de Distribuição e o Agente de Mesclagem se conectam do Distribuidor ao Assinante. Isso só se aplica a versões anteriores do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55d8b-106">The context under which the Distribution Agent and Merge Agent connect from the Distributor to the Subscriber This applies only to versions before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="55d8b-107">Selecione **Representar conta de processo do agente** para efetuar conexões com o Assinante usando o contexto de conta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no Distribuidor ou especifique **Autenticação do SQL Server**e insira um valor para **Logon** e **Senha**.</span><span class="sxs-lookup"><span data-stu-id="55d8b-107">Select **Impersonate agent process account** to make connections to the Subscriber using the context of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent account at the Distributor, or specify **SQL Server Authentication**, and then enter a value for **Login** and **Password**.</span></span> <span data-ttu-id="55d8b-108">A[!INCLUDE[msCoName](../../includes/msconame-md.md)] recomenda que você selecione **Representar conta de processo do agente**.</span><span class="sxs-lookup"><span data-stu-id="55d8b-108">[!INCLUDE[msCoName](../../includes/msconame-md.md)] recommends that you select **Impersonate agent process account**.</span></span>  
  
 <span data-ttu-id="55d8b-109">Para o [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versões posteriores, as informações de conexão são especificadas para cada assinatura no Assistente para Nova Assinatura e pode ser alterada na caixa de diálogo **Propriedades da Assinatura** .</span><span class="sxs-lookup"><span data-stu-id="55d8b-109">For [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions, connection information is specified for each subscription in the New Subscription Wizard and can be changed in the **Subscription Properties** dialog box.</span></span>  
  
 <span data-ttu-id="55d8b-110">**Agendamentos Padrão de Agente**</span><span class="sxs-lookup"><span data-stu-id="55d8b-110">**Default Agent Schedules**</span></span>  
 <span data-ttu-id="55d8b-111">O agendamento padrão usado no Assistente para Nova Assinatura para Assinantes que executam versões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anteriores ao [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55d8b-111">The default schedule used in the New Subscription Wizard for Subscribers running versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span>  
  
 <span data-ttu-id="55d8b-112">**Diversos**</span><span class="sxs-lookup"><span data-stu-id="55d8b-112">**Miscellaneous**</span></span>  
 <span data-ttu-id="55d8b-113">Inclui informações sobre o Assinante e o tipo de Assinante.</span><span class="sxs-lookup"><span data-stu-id="55d8b-113">Includes information on the Subscriber and Subscriber type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55d8b-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="55d8b-114">See Also</span></span>  
 [<span data-ttu-id="55d8b-115">Exibir e modificar propriedades de Publicador e Distribuidor</span><span class="sxs-lookup"><span data-stu-id="55d8b-115">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)   

 [<span data-ttu-id="55d8b-116">Assinar publicações</span><span class="sxs-lookup"><span data-stu-id="55d8b-116">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
