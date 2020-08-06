---
title: Funções e permissões (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- access controls [Reporting Services]
- permissions [Reporting Services], about permissions
- security [Reporting Services], identity and access control
- authentication [Reporting Services]
- permissions [Reporting Services]
- security [Reporting Services], role-based
- identity [Reporting Services]
ms.assetid: eea655fe-43ed-418d-8233-b288a8f4daa4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0e6098a51afde04164e3ef0dfa5e5297457b4440
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574482"
---
# <a name="roles-and-permissions-reporting-services"></a><span data-ttu-id="823b6-102">Funções e permissões (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="823b6-102">Roles and Permissions (Reporting Services)</span></span>
  <span data-ttu-id="823b6-103">O Reporting Services fornece um subsistema de autenticação e modelo de autorização com base na função.</span><span class="sxs-lookup"><span data-stu-id="823b6-103">Reporting Services provides an authentication subsystem and role-based authorization model.</span></span> <span data-ttu-id="823b6-104">Os modelos de autenticação e autorização variam, dependendo se o servidor de relatório é executado no modo nativo ou no modo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="823b6-104">Authentication and authorization models vary depending on whether the report server runs in native mode or SharePoint mode.</span></span> <span data-ttu-id="823b6-105">Se o servidor de relatório fizer parte de uma implantação do SharePoint, as permissões do SharePoint determinarão quem tem acesso ao servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="823b6-105">If the report server is part of a SharePoint deployment, SharePoint permissions determine who has access to the report server.</span></span>  
  
## <a name="identity-and-access-control-for-native-mode"></a><span data-ttu-id="823b6-106">Controle de identidade e acesso para o modo nativo</span><span class="sxs-lookup"><span data-stu-id="823b6-106">Identity and Access Control for Native Mode</span></span>  
 <span data-ttu-id="823b6-107">A autenticação padrão se baseia na Autenticação e na segurança integrada do Windows.</span><span class="sxs-lookup"><span data-stu-id="823b6-107">Default authentication is based on Windows Authentication and integrated security.</span></span> <span data-ttu-id="823b6-108">Você pode alterar as configurações de autenticação para permitir que o servidor de relatório responda a solicitações de autenticação diferentes, ou mesmo substitua os recursos de segurança padrão por uma extensão de autenticação personalizada fornecida por você.</span><span class="sxs-lookup"><span data-stu-id="823b6-108">You can change the authentication settings to allow the report server to respond to different authentication requests, or even replace the default security features with a custom authentication extension that you provide.</span></span>  
  
 <span data-ttu-id="823b6-109">A autorização se baseia em funções que você atribui a um princípio.</span><span class="sxs-lookup"><span data-stu-id="823b6-109">Authorization is based on roles that you assign to a principle.</span></span> <span data-ttu-id="823b6-110">Cada função consiste em um conjunto de tarefas relacionadas compostas, por sua vez, por operações relacionadas.</span><span class="sxs-lookup"><span data-stu-id="823b6-110">Each role consists of a set of related tasks, which are in turn composed of related operations.</span></span> <span data-ttu-id="823b6-111">Por exemplo, a tarefa **Gerenciar relatórios** concede acesso às seguintes operações de servidor de relatório: exibir relatórios, adicionar relatório, atualizar relatório, excluir relatório, agendar relatório e atualizar propriedades de relatório.</span><span class="sxs-lookup"><span data-stu-id="823b6-111">For example, the **Manage reports** task grants access to the following report server operations: view reports, add report, update report, delete report, schedule report, and update report properties.</span></span>  
  
## <a name="identity-and-access-control-for-sharepoint-mode"></a><span data-ttu-id="823b6-112">Controle de identidade e acesso no modo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="823b6-112">Identity and Access Control for SharePoint Mode</span></span>  
 <span data-ttu-id="823b6-113">No modo integrado do SharePoint, a autenticação e a autorização são manipuladas no site do SharePoint, antes da chegada das solicitações ao servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="823b6-113">In SharePoint integrated mode, authentication and authorization are handled on the SharePoint site, before requests reach the report server.</span></span> <span data-ttu-id="823b6-114">De acordo com o modo como você configura a autenticação, as solicitações de um site do SharePoint contêm um token de segurança ou um nome de usuário confiável.</span><span class="sxs-lookup"><span data-stu-id="823b6-114">Depending on how you configure authentication, requests from a SharePoint site include a security token or a trusted user name.</span></span> <span data-ttu-id="823b6-115">As permissões que você define para usuários e grupos do SharePoint autorizam o acesso aos itens do servidor de relatório colocados nas bibliotecas do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="823b6-115">Permissions that you set for SharePoint users and groups authorize access to report server items that are placed in SharePoint libraries.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="823b6-116">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="823b6-116">In This Section</span></span>  
 [<span data-ttu-id="823b6-117">Conceder permissões em um servidor de relatório no Modo Nativo</span><span class="sxs-lookup"><span data-stu-id="823b6-117">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
 <span data-ttu-id="823b6-118">Descreve o modelo de autorização com base em funções que fornece acesso a conteúdo e operações.</span><span class="sxs-lookup"><span data-stu-id="823b6-118">Describes the role-based authorization model that provides access to content and operations.</span></span>  
  
 [<span data-ttu-id="823b6-119">Conceder permissões para itens do servidor de relatório em um site do SharePoint</span><span class="sxs-lookup"><span data-stu-id="823b6-119">Granting Permissions on Report Server Items on a SharePoint Site</span></span>](granting-permissions-on-report-server-items-on-a-sharepoint-site.md)  
 <span data-ttu-id="823b6-120">Explica como grupos, níveis de permissão e permissões do SharePoint são usados para controlar o acesso a um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="823b6-120">Explains how SharePoint groups, permission levels, and permissions are used to control access to a report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="823b6-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="823b6-121">See Also</span></span>  
 <span data-ttu-id="823b6-122">[Autenticação com o servidor de relatório](authentication-with-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="823b6-122">[Authentication with the Report Server](authentication-with-the-report-server.md) </span></span>  
 [<span data-ttu-id="823b6-123">Conceder permissões em um servidor de relatório no Modo Nativo</span><span class="sxs-lookup"><span data-stu-id="823b6-123">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
  
  
