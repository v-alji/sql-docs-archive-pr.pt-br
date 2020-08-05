---
title: Informações do servidor Web | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.webserverinformation.f1
ms.assetid: 86d72275-45c7-459f-98cf-f5a366ed279c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f7b461ed26b3e234f083add3312e256e164efc9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572475"
---
# <a name="web-server-information"></a><span data-ttu-id="f1247-102">Informações do Servidor Web</span><span class="sxs-lookup"><span data-stu-id="f1247-102">Web Server Information</span></span>
  <span data-ttu-id="f1247-103">As informações do servidor Web são necessárias ao usar a opção de sincronização da Web para replicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="f1247-103">Web server information is required to use the Web synchronization option for merge replication.</span></span> <span data-ttu-id="f1247-104">Para obter mais informações sobre como configurar a sincronização da Web, consulte [Configurar sincronização da Web](configure-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="f1247-104">For information about configuring Web synchronization, see [Configure Web Synchronization](configure-web-synchronization.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f1247-105">Opções</span><span class="sxs-lookup"><span data-stu-id="f1247-105">Options</span></span>  
 <span data-ttu-id="f1247-106">**Endereço do servidor Web**</span><span class="sxs-lookup"><span data-stu-id="f1247-106">**Web server address**</span></span>  
 <span data-ttu-id="f1247-107">Se tiver especificado um endereço do servidor Web na página **Instantâneo de FTP e Internet** da caixa de diálogo **Propriedades de Publicação**, ele será exibido nessa caixa de texto como padrão.</span><span class="sxs-lookup"><span data-stu-id="f1247-107">If you specified a Web server address in the **FTP Snapshot andInternet** page of the **Publication Properties** dialog box, it appears in this text box as a default.</span></span> <span data-ttu-id="f1247-108">Aceite o padrão ou insira um endereço do servidor Web completamente qualificado para o servidor IIS (Serviços de Informações da Internet) da [!INCLUDE[msCoName](../../includes/msconame-md.md)] que sincroniza com essa assinatura.</span><span class="sxs-lookup"><span data-stu-id="f1247-108">Either accept the default or enter a fully qualified Web server address for the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) server that synchronizes this subscription.</span></span>  
  
 <span data-ttu-id="f1247-109">**Como cada Assinante se conectará ao servidor Web?**</span><span class="sxs-lookup"><span data-stu-id="f1247-109">**How will each Subscriber connect to the Web server?**</span></span>  
 <span data-ttu-id="f1247-110">Especifique o tipo de autenticação usado para conexão com o servidor Web.</span><span class="sxs-lookup"><span data-stu-id="f1247-110">Specify the type of authentication used to connect to the Web server.</span></span> <span data-ttu-id="f1247-111">Recomendamos o uso da Autenticação Básica para conexões com o servidor IIS junto com o SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="f1247-111">It is recommended to use Basic Authentication for connections to the IIS server in conjunction with Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="f1247-112">Se você selecionar Autenticação Básica, insira o logon e a senha que serão usados para conexão do Assinante com o servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="f1247-112">If you select Basic Authentication, enter the login and password that will be used to connect from the Subscriber to the IIS server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1247-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f1247-113">See Also</span></span>  
 <span data-ttu-id="f1247-114">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="f1247-114">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="f1247-115">[Exibir e modificar propriedades de assinatura pull](view-and-modify-pull-subscription-properties.md) </span><span class="sxs-lookup"><span data-stu-id="f1247-115">[View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md) </span></span>  
 <span data-ttu-id="f1247-116">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span><span class="sxs-lookup"><span data-stu-id="f1247-116">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span></span>  
 <span data-ttu-id="f1247-117">[Subscribe to Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="f1247-117">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 [<span data-ttu-id="f1247-118">Sincronização da Web para replicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="f1247-118">Web Synchronization for Merge Replication</span></span>](web-synchronization-for-merge-replication.md)  
  
  
