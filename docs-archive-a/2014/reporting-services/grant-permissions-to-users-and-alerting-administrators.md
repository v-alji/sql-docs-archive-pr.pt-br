---
title: Conceder permissões a usuários e administradores de alerta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 166808e1-ada7-48d2-bda8-8f7c017fb3aa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5bf7f030871287379ce9fb32a1789b95cff0fc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582828"
---
# <a name="grant-permissions-to-users-and-alerting-administrators"></a><span data-ttu-id="ed300-102">Conceder permissões a usuários e administradores de alerta</span><span class="sxs-lookup"><span data-stu-id="ed300-102">Grant Permissions to Users and Alerting Administrators</span></span>
  <span data-ttu-id="ed300-103">Para que os usuários e os administradores de alerta possam criar, editar, excluir e exibir alertas de dados, eles devem receber permissões do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ed300-103">Before users and alerting administrators can create, edit, delete, and view data alerts they must be granted SharePoint permissions.</span></span> <span data-ttu-id="ed300-104">Não há nenhuma permissão especial a ser usada com o recurso de alerta de dados do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] . Você usa as permissões internas do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ed300-104">There are no special permissions to use with the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] data alerting feature, you use the built-in SharePoint permissions.</span></span>  
  
 <span data-ttu-id="ed300-105">**Operadores de informações** – as permissões precisam incluir as permissões Criar Alerta e Exibir Itens do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ed300-105">**Information workers**-Permissions must include the Create Alert and View Items SharePoint permissions.</span></span> <span data-ttu-id="ed300-106">Os níveis de permissão internos do SharePoint denominados Design, Colaborar, Ler e Apenas Exibir incluem as permissões Criar Alerta e Exibir Itens do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ed300-106">The built-in SharePoint permission levels named Design, Contribute, Read, and View Only include the Create Alert and View Items SharePoint permissions.</span></span> <span data-ttu-id="ed300-107">Você também pode criar um nível de permissão personalizado com as permissões necessárias dar suporte a usuários que criam, editam, executam e exibem alertas de dados.</span><span class="sxs-lookup"><span data-stu-id="ed300-107">You can also create a custom permission level with the permissions required to support users that create, edit, run, and view data alerts.</span></span>  
  
 <span data-ttu-id="ed300-108">**Administradores de alerta**-as permissões devem incluir a permissão gerenciar alerta do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ed300-108">**Alerting administrators**-Permissions must include the Manage Alert SharePoint permission.</span></span> <span data-ttu-id="ed300-109">Por padrão, apenas o nível de permissão Controle Completo inclui essa permissão para sites criados com o modelo de Site de Equipe.</span><span class="sxs-lookup"><span data-stu-id="ed300-109">By default only the Full Control permission level includes this permission for sites created with the Team Site site template.</span></span> <span data-ttu-id="ed300-110">Se você usar outros modelos de sites, visualizará listas diferentes de grupos padrão do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ed300-110">If you use other site templates, you will see different lists of default SharePoint groups.</span></span> <span data-ttu-id="ed300-111">Você pode adicionar a permissão Gerenciar Alerta a um dos níveis de permissão internos ou criar um nível de permissão personalizado com a permissão necessária para dar suporte a administradores de alerta que exibem e excluem alertas de dados.</span><span class="sxs-lookup"><span data-stu-id="ed300-111">You can add the Manage Alert permission to one of the built-in permission levels or create a custom permission level with the permission required to support alerting administrators that view and delete data alerts.</span></span>  
  
 <span data-ttu-id="ed300-112">Para obter mais informações sobre as permissões do SharePoint, consulte [Permissões de usuários e níveis de permissão (SharePoint Server 2010)](https://technet.microsoft.com/library/cc721640.aspx).</span><span class="sxs-lookup"><span data-stu-id="ed300-112">To learn more about SharePoint permissions, see [User permissions and permission levels (SharePoint Server 2010)](https://technet.microsoft.com/library/cc721640.aspx).</span></span>  
  
### <a name="to-grant-permissions"></a><span data-ttu-id="ed300-113">Para conceder permissões</span><span class="sxs-lookup"><span data-stu-id="ed300-113">To grant permissions</span></span>  
  
1.  <span data-ttu-id="ed300-114">Vá para o site do SharePoint ao qual você deseja conceder permissões.</span><span class="sxs-lookup"><span data-stu-id="ed300-114">Go to the SharePoint site to which you want to grant permissions.</span></span>  
  
2.  <span data-ttu-id="ed300-115">Na barra de ferramentas, clique em **Ações do Site** e clique em **Permissões do Site**.</span><span class="sxs-lookup"><span data-stu-id="ed300-115">On the toolbar, click **Site Actions** and then click **Site Permissions**.</span></span>  
  
     <span data-ttu-id="ed300-116">Se você não vir essa opção, você não terá permissão suficiente para conceder permissões a outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="ed300-116">If you do not see this option, you do not sufficient permission to grant permissions to others.</span></span>  
  
3.  <span data-ttu-id="ed300-117">Clique em **Conceder Permissões**.</span><span class="sxs-lookup"><span data-stu-id="ed300-117">Click **Grant Permissions**.</span></span>  
  
4.  <span data-ttu-id="ed300-118">Em **Usuários/Grupos**, digite os nomes dos usuários, os nomes dos grupos ou os endereços de email aos quais você quer conceder permissão.</span><span class="sxs-lookup"><span data-stu-id="ed300-118">In **Users/Groups**, type the user names, group names, or e-mail addresses you want grant permission to.</span></span>  
  
5.  <span data-ttu-id="ed300-119">Selecione a opção **Adicionar usuários a um grupo do SharePoint** ou **Conceder permissão a usuários diretamente** .</span><span class="sxs-lookup"><span data-stu-id="ed300-119">Select the **Add users to a SharePoint group** or **Grant users permission directly** option.</span></span> <span data-ttu-id="ed300-120">Dependendo se você selecionou **Adicionar usuários a um grupo do SharePoint** ou **Conceder permissões aos usuários diretamente** , siga em destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="ed300-120">Depending on whether you selected **Add users to a SharePoint group** or **Grant users permissions directly** do one of the following:</span></span>  
  
    -   <span data-ttu-id="ed300-121">Se você tiver selecionado **Adicionar usuários a um grupo do SharePoint**, selecione um nível de permissão na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="ed300-121">If you selected **Add users to a SharePoint group**, select a permission level in the drop-down list.</span></span>  
  
    -   <span data-ttu-id="ed300-122">Se você tiver selecionado **Conceder permissões a usuários diretamente**, selecione um nível de permissão.</span><span class="sxs-lookup"><span data-stu-id="ed300-122">If you selected **Grant users permissions directly**, select a permission level.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ed300-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ed300-123">See Also</span></span>  
 <span data-ttu-id="ed300-124">[Definir permissões para itens do servidor de relatório em um site do SharePoint &#40;Reporting Services no modo integrado do SharePoint&#41;](security/set-permissions-for-report-server-items-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="ed300-124">[Set Permissions for Report Server Items on a SharePoint Site &#40;Reporting Services in SharePoint Integrated Mode&#41;](security/set-permissions-for-report-server-items-on-a-sharepoint-site.md) </span></span>  
 [<span data-ttu-id="ed300-125">Alertas de dados do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ed300-125">Reporting Services Data Alerts</span></span>](../ssms/agent/alerts.md)  
  
  
