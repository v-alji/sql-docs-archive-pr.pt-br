---
title: Distribuição de relatório de controle | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [Reporting Services], report distribution
- subscriptions [Reporting Services], e-mail
- subscriptions [Reporting Services], file share delivery
- file share delivery [Reporting Services]
- e-mail [Reporting Services]
- subscriptions [Reporting Services], security
- mail [Reporting Services]
ms.assetid: 8f15e2c6-a647-4b05-a519-1743b5d8654c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: de8a27801ef89f10bf303cee17d1c2d0e1081c5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568354"
---
# <a name="control-report-distribution"></a><span data-ttu-id="ba8d0-102">Controlar a distribuição de relatórios</span><span class="sxs-lookup"><span data-stu-id="ba8d0-102">Control Report Distribution</span></span>
  <span data-ttu-id="ba8d0-103">Você pode configurar um servidor de relatório para reduzir os riscos de segurança associados à distribuição de emails e de compartilhamentos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="ba8d0-103">You can configure a report server to reduce the security risks associated with e-mail and file share distribution.</span></span>  
  
## <a name="securing-reports"></a><span data-ttu-id="ba8d0-104">Protegendo relatórios</span><span class="sxs-lookup"><span data-stu-id="ba8d0-104">Securing Reports</span></span>  
 <span data-ttu-id="ba8d0-105">A primeira etapa para controlar a distribuição de relatório é proteger o relatório contra o acesso não autorizado.</span><span class="sxs-lookup"><span data-stu-id="ba8d0-105">The first step in controlling report distribution is to secure the report against unauthorized access.</span></span> <span data-ttu-id="ba8d0-106">Para ser usado em uma assinatura, o relatório deve usar um conjunto armazenado de credenciais que não variam para entregas individuais.</span><span class="sxs-lookup"><span data-stu-id="ba8d0-106">To be used in a subscription, a report must use a stored set of credentials that do not vary for individual deliveries.</span></span> <span data-ttu-id="ba8d0-107">Qualquer usuário que pode acessar o relatório no servidor de relatório pode executá-lo e possivelmente distribuí-lo.</span><span class="sxs-lookup"><span data-stu-id="ba8d0-107">Any user who can access the report on the report server can run it and possibly distribute it.</span></span> <span data-ttu-id="ba8d0-108">Para impedir que isto aconteça, você deve limitar o acesso somente aos usuários que precisam do relatório.</span><span class="sxs-lookup"><span data-stu-id="ba8d0-108">To prevent this from occurring, you must limit report access to only those users who require it.</span></span> <span data-ttu-id="ba8d0-109">Para obter mais informações, consulte [proteger relatórios e recursos](security/secure-reports-and-resources.md) e [pastas seguras](security/secure-folders.md).</span><span class="sxs-lookup"><span data-stu-id="ba8d0-109">For more information, see [Secure Reports and Resources](security/secure-reports-and-resources.md) and [Secure Folders](security/secure-folders.md).</span></span>  
  
 <span data-ttu-id="ba8d0-110">Relatórios extremamente confidenciais que usam a segurança de banco de dados para autorizar o acesso não podem ser distribuídos por meio de assinaturas.</span><span class="sxs-lookup"><span data-stu-id="ba8d0-110">Highly confidential reports that use database security to authorize access cannot be distributed by way of subscription.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ba8d0-111">Os relatórios são transportados como arquivos.</span><span class="sxs-lookup"><span data-stu-id="ba8d0-111">Reports are transported as files.</span></span> <span data-ttu-id="ba8d0-112">Os riscos e as proteções que se aplicam aos arquivos também se aplicam aos relatórios salvos em disco ou enviados como anexos.</span><span class="sxs-lookup"><span data-stu-id="ba8d0-112">The risks and safeguards that apply to files apply equally to reports that are saved to disk or sent as attachments.</span></span> <span data-ttu-id="ba8d0-113">Qualquer usuário que tem acesso a um arquivo pode distribuir ou usar o arquivo como desejar.</span><span class="sxs-lookup"><span data-stu-id="ba8d0-113">Any user who has access to a file can distribute or use the file at his or her discretion.</span></span>  
  
## <a name="controlling-e-mail-delivery"></a><span data-ttu-id="ba8d0-114">Controlando a entrega de emails</span><span class="sxs-lookup"><span data-stu-id="ba8d0-114">Controlling E-Mail Delivery</span></span>  
 <span data-ttu-id="ba8d0-115">Você pode configurar um servidor de relatório para limitar a distribuição de emails a domínios host específicos.</span><span class="sxs-lookup"><span data-stu-id="ba8d0-115">You can configure a report server to limit e-mail distribution to specific host domains.</span></span> <span data-ttu-id="ba8d0-116">Por exemplo, é possível impedir que um servidor de relatório entregue um relatório para todos os domínios, com exceção dos listados no arquivo de configuração RSReportServer.</span><span class="sxs-lookup"><span data-stu-id="ba8d0-116">For example, you can prevent a report server from delivering a report to all domains except those listed in the RSReportServer configuration file.</span></span>  
  
 <span data-ttu-id="ba8d0-117">Você também pode definir configurações para ocultar o campo **Para** em uma assinatura.</span><span class="sxs-lookup"><span data-stu-id="ba8d0-117">You can also set configuration settings to hide the **To** field in a subscription.</span></span> <span data-ttu-id="ba8d0-118">Neste caso, os relatórios são entregues somente ao usuário que define a assinatura.</span><span class="sxs-lookup"><span data-stu-id="ba8d0-118">In this case, reports are delivered only to the user defining the subscription.</span></span> <span data-ttu-id="ba8d0-119">No entanto, depois que um relatório é enviado a um usuário, você não pode impedir explicitamente seu encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="ba8d0-119">However, after a report is sent to a user, you cannot explicitly prevent it from being forwarded.</span></span>  
  
 <span data-ttu-id="ba8d0-120">A maneira mais eficaz de controlar a distribuição de relatórios é configurar um servidor de relatório para enviar somente uma URL de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="ba8d0-120">The most effective way to control report distribution is to configure a report server to send only a report server URL.</span></span> <span data-ttu-id="ba8d0-121">O servidor de relatório usa a Autenticação do Windows e um modelo de autorização baseado em funções para controlar o acesso a um relatório.</span><span class="sxs-lookup"><span data-stu-id="ba8d0-121">The report server uses Windows Authentication and a role-based authorization model to control access to a report.</span></span> <span data-ttu-id="ba8d0-122">Se o usuário receber automaticamente por email um relatório que não tem autorização para exibir, o servidor de relatório não exibirá o relatório.</span><span class="sxs-lookup"><span data-stu-id="ba8d0-122">If a user accidentally receives through e-mail a report that he or she is not authorized to view, the report server will not display the report.</span></span>  
  
## <a name="controlling-file-share-delivery"></a><span data-ttu-id="ba8d0-123">Controlando a entrega de compartilhamentos de arquivos</span><span class="sxs-lookup"><span data-stu-id="ba8d0-123">Controlling File Share Delivery</span></span>  
 <span data-ttu-id="ba8d0-124">A entrega de compartilhamentos de arquivos é usada para enviar um relatório a um arquivo em um disco rígido.</span><span class="sxs-lookup"><span data-stu-id="ba8d0-124">File share delivery is used to send a report to a file on a hard disk.</span></span> <span data-ttu-id="ba8d0-125">Depois de ser salvo em disco, o arquivo não pode mais ser submetido ao modelo de segurança baseado em funções que o servidor de relatório usa para controlar o acesso do usuário.</span><span class="sxs-lookup"><span data-stu-id="ba8d0-125">After the file has been saved to disk, it is no longer subject to the role-based security model that the report server uses to control user access.</span></span> <span data-ttu-id="ba8d0-126">Para proteger um relatório que foi entregue em disco, coloque listas de controle de acesso (ACLs) no próprio arquivo ou na pasta que o contém.</span><span class="sxs-lookup"><span data-stu-id="ba8d0-126">To secure a report that has been delivered to disk, you can place Access Control Lists (ACLs) on the file itself or on the folder that contains it.</span></span> <span data-ttu-id="ba8d0-127">Opções de segurança adicionais podem estar disponíveis, dependendo do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="ba8d0-127">Additional security options might be available, depending on your operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba8d0-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ba8d0-128">See Also</span></span>  
 <span data-ttu-id="ba8d0-129">[Configurar um servidor de relatório para entrega de email &#40;Configuration Manager SSRS&#41;](../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="ba8d0-129">[Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;](../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="ba8d0-130">[Assinaturas e entrega &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="ba8d0-130">[Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span></span>  
 [<span data-ttu-id="ba8d0-131">Criar e gerenciar assinaturas de servidores de relatório no modo Nativo</span><span class="sxs-lookup"><span data-stu-id="ba8d0-131">Create and Manage Subscriptions for Native Mode Report Servers</span></span>](../../2014/reporting-services/create-manage-subscriptions-native-mode-report-servers.md)  
  
  
