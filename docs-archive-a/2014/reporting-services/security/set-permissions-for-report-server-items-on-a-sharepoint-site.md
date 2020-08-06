---
title: Definir permissões para itens do servidor de relatório em um site do SharePoint (Reporting Services no modo integrado do SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- permissions [Reporting Services], SharePoint integrated mode
- SharePoint integration [Reporting Services], permissions
ms.assetid: 2467c657-a3bf-4ec3-a88c-8877df19823d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f38497843ca99342f13952153d7fed957564e006
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679655"
---
# <a name="set-permissions-for-report-server-items-on-a-sharepoint-site-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="c10ca-102">Definir permissões para itens de servidor de relatório em um site do SharePoint (Reporting Services no modo integrado do SharePoint)</span><span class="sxs-lookup"><span data-stu-id="c10ca-102">Set Permissions for Report Server Items on a SharePoint Site (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="c10ca-103">Se as configurações de segurança padrão não fornecerem o nível de acesso desejado, você poderá criar novos níveis de permissão para fornecer acesso a itens ou operações específicos do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="c10ca-103">If default security settings do not provide the level of access that you require, you can create new permission levels to provide access to specific report server items or operations.</span></span> <span data-ttu-id="c10ca-104">As configurações de segurança personalizadas podem ser úteis se você quiser restringir o acesso a um determinado relatório.</span><span class="sxs-lookup"><span data-stu-id="c10ca-104">Custom security settings can be useful if you want to restrict access to a particular report.</span></span>  
  
 <span data-ttu-id="c10ca-105">Você deve ser um proprietário de site para criar níveis de permissão e grupos.</span><span class="sxs-lookup"><span data-stu-id="c10ca-105">You must be a site owner to create permission levels and groups.</span></span> <span data-ttu-id="c10ca-106">Níveis de permissão são usados em todo o site.</span><span class="sxs-lookup"><span data-stu-id="c10ca-106">Permission levels are used globally throughout a site.</span></span> <span data-ttu-id="c10ca-107">Se um novo nível de permissão for criado, estará disponível para outros proprietários de site.</span><span class="sxs-lookup"><span data-stu-id="c10ca-107">If you create a new permission level, it will be available to other site owners.</span></span>  
  
 <span data-ttu-id="c10ca-108">A maioria das permissões é herdada de um site pai.</span><span class="sxs-lookup"><span data-stu-id="c10ca-108">Most permissions are inherited from a parent site.</span></span> <span data-ttu-id="c10ca-109">Se você atribuir permissões em uma biblioteca ou item específico, a herança de permissões será quebrada, acarretando uma sobrecarga adicional no gerenciamento de permissões para essa ramificação da hierarquia do seu site.</span><span class="sxs-lookup"><span data-stu-id="c10ca-109">If you assign permissions on a specific library or item, you break permission inheritance and incur additional overhead in how manage permissions for that branch of your site hierarchy.</span></span>  
  
 <span data-ttu-id="c10ca-110">É possível definir permissões em arquivos de definição de relatório (.rdl), modelo (.smdl) e fonte de dados compartilhados (.rsds).</span><span class="sxs-lookup"><span data-stu-id="c10ca-110">You can set permissions on report definition (.rdl), model (.smdl), and shared data source (.rsds) files.</span></span> <span data-ttu-id="c10ca-111">Não é possível combinar permissões herdadas e gerenciadas no mesmo item.</span><span class="sxs-lookup"><span data-stu-id="c10ca-111">You cannot combine inherited and managed permissions on the same item.</span></span> <span data-ttu-id="c10ca-112">Se você optar por gerenciar permissões diretamente, as permissões herdadas não afetarão o item atual.</span><span class="sxs-lookup"><span data-stu-id="c10ca-112">If you choose to manage permissions directly, inherited permissions will have no effect on the current item.</span></span> <span data-ttu-id="c10ca-113">Se desejar retomar a herança de permissões posteriormente, selecione **Herdar Permissões** no menu **Ações** .</span><span class="sxs-lookup"><span data-stu-id="c10ca-113">If you want to resume permission inheritance later, you can select **Inherit Permissions** on the **Actions** menu.</span></span>  
  
 <span data-ttu-id="c10ca-114">Para definir permissões em entidades e perspectivas em um modelo, você deve ter o nível de permissão Controle Total no modelo.</span><span class="sxs-lookup"><span data-stu-id="c10ca-114">To set permissions on entities and perspectives in a model, you must have Full Control level of permission for the model.</span></span> <span data-ttu-id="c10ca-115">O nível Controle Total inclui a tarefa “Gerenciar Permissões”, uma permissão no nível do site concedida aos proprietários do site e outros grupos do SharePoint que possuem o nível de permissão Controle Total.</span><span class="sxs-lookup"><span data-stu-id="c10ca-115">Full Control includes "Manage Permissions", which is a site level permission that is granted to site owners and other SharePoint groups who have Full Control level of permission.</span></span> <span data-ttu-id="c10ca-116">Se desejar que usuários específicos possam definir a segurança do item de modelo, interrompa a herança de permissões e conceda permissões elevadas (como Controle Total) ao usuário ou grupo no arquivo do modelo.</span><span class="sxs-lookup"><span data-stu-id="c10ca-116">If you want to offer specific users the ability to set model item security, you must break permission inheritance and grant elevated permissions (such as Full Control) to the user or group on the model file.</span></span> <span data-ttu-id="c10ca-117">Ao conceder Controle Total em um item, como um arquivo da biblioteca, as permissões são delimitadas para esse item e não se estendem ao pai ou a outros itens da mesma biblioteca.</span><span class="sxs-lookup"><span data-stu-id="c10ca-117">When you grant Full Control on an item such as a file in the library, the permissions are scoped to that item and do not extend to the parent or to other items within the same library.</span></span> <span data-ttu-id="c10ca-118">Depois que o usuário tiver a permissão Gerenciar Permissões no modelo, poderá usar a segurança do item de modelo por meio do site do SharePoint ou do Designer de Modelo.</span><span class="sxs-lookup"><span data-stu-id="c10ca-118">After the user has Manage Permissions permission on the model, he or she can use set model item security via the SharePoint site or Model Designer.</span></span>  
  
### <a name="to-set-permissions-on-an-individual-report-model-or-data-source"></a><span data-ttu-id="c10ca-119">Para definir permissões em um relatório, modelo ou fonte de dados individual</span><span class="sxs-lookup"><span data-stu-id="c10ca-119">To set permissions on an individual report, model, or data source</span></span>  
  
1.  <span data-ttu-id="c10ca-120">Se a biblioteca ainda não estiver aberta, clique no seu nome no Início Rápido.</span><span class="sxs-lookup"><span data-stu-id="c10ca-120">If the library is not already open, click its name on the Quick Launch.</span></span> <span data-ttu-id="c10ca-121">Se o nome da biblioteca não for exibido, clique em **Exibir Todo o Conteúdo do Site**e, em seguida, clique no nome da biblioteca.</span><span class="sxs-lookup"><span data-stu-id="c10ca-121">If the name of your library does not appear, click **View All Site Content**, and then click the name of your library.</span></span>  
  
2.  <span data-ttu-id="c10ca-122">Aponte para o arquivo de relatório, modelo do relatório ou fonte de dados compartilhados.</span><span class="sxs-lookup"><span data-stu-id="c10ca-122">Point to the report, report model, or shared data source file.</span></span>  
  
3.  <span data-ttu-id="c10ca-123">Clique na seta para baixo e, no menu, clique em **Gerenciar Permissões**.</span><span class="sxs-lookup"><span data-stu-id="c10ca-123">Click the down arrow, and on the menu, click **Manage Permissions**.</span></span>  
  
4.  <span data-ttu-id="c10ca-124">No menu **Ações** , clique em **Editar Permissões**e em **OK** para confirmar a ação.</span><span class="sxs-lookup"><span data-stu-id="c10ca-124">On the **Actions** menu, click **Edit Permissions**, and then click **OK** to confirm the action.</span></span>  
  
5.  <span data-ttu-id="c10ca-125">Para atribuir permissões a um usuário ou grupo que ainda não possua permissões para usar o arquivo, clique em **Novo**e em **Adicionar Usuários**.</span><span class="sxs-lookup"><span data-stu-id="c10ca-125">To give permissions to a user or group that does not yet have permissions to use the file, click **New**, and then click **Add Users**.</span></span>  
  
6.  <span data-ttu-id="c10ca-126">Para remover ou modificar permissões para um usuário ou grupo existente, clique na caixa de seleção ao lado do usuário ou grupo, clique em **Ações**e, em seguida, clique em **Remover Permissões do Usuário** ou **Editar Permissões do Usuário**.</span><span class="sxs-lookup"><span data-stu-id="c10ca-126">To remove or modify permissions for an existing user or group, click the check box next to the user or group, click **Actions**, and then click **Remove User Permissions** or **Edit User Permissions**.</span></span>  
  
### <a name="to-set-permissions-that-enable-model-item-security"></a><span data-ttu-id="c10ca-127">Para definir permissões que habilitam a segurança do item de modelo</span><span class="sxs-lookup"><span data-stu-id="c10ca-127">To set permissions that enable model item security</span></span>  
  
1.  <span data-ttu-id="c10ca-128">Faça logon no site do SharePoint usando uma conta que tenha a permissão Gerenciar Permissões no site.</span><span class="sxs-lookup"><span data-stu-id="c10ca-128">Log in to the SharePoint site using an account that has Manage Permissions permission on the site.</span></span>  
  
2.  <span data-ttu-id="c10ca-129">Abra a biblioteca que contém o modelo.</span><span class="sxs-lookup"><span data-stu-id="c10ca-129">Open the library that contains the model.</span></span>  
  
3.  <span data-ttu-id="c10ca-130">Aponte para o modelo.</span><span class="sxs-lookup"><span data-stu-id="c10ca-130">Point to the model.</span></span>  
  
4.  <span data-ttu-id="c10ca-131">Clique na seta para baixo ao lado do modelo e clique em **Gerenciar Permissões**.</span><span class="sxs-lookup"><span data-stu-id="c10ca-131">Click the down arrow next to the model, and click **Manage Permissions**.</span></span>  
  
5.  <span data-ttu-id="c10ca-132">Clique em **Ações**.</span><span class="sxs-lookup"><span data-stu-id="c10ca-132">Click **Actions**.</span></span>  
  
6.  <span data-ttu-id="c10ca-133">Clique em **Editar Permissões**.</span><span class="sxs-lookup"><span data-stu-id="c10ca-133">Click **Edit Permissions**.</span></span> <span data-ttu-id="c10ca-134">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c10ca-134">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="c10ca-135">Clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="c10ca-135">Click **New**.</span></span>  
  
8.  <span data-ttu-id="c10ca-136">Clique em **Adicionar Usuários**.</span><span class="sxs-lookup"><span data-stu-id="c10ca-136">Click **Add Users**.</span></span>  
  
9. <span data-ttu-id="c10ca-137">Em Usuários/Grupos, insira a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="c10ca-137">In Users/Groups, enter the user account.</span></span>  
  
10. <span data-ttu-id="c10ca-138">Selecione **Dar permissões a usuários diretamente**.</span><span class="sxs-lookup"><span data-stu-id="c10ca-138">Select **Give users permission directly**.</span></span>  
  
11. <span data-ttu-id="c10ca-139">Clique em **Controle Total**.</span><span class="sxs-lookup"><span data-stu-id="c10ca-139">Click **Full Control**.</span></span>  
  
12. <span data-ttu-id="c10ca-140">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c10ca-140">Click **OK**.</span></span> <span data-ttu-id="c10ca-141">Após o usuário conseguir gerenciar permissões para um modelo específico, poderá abrir o modelo para editar permissões.</span><span class="sxs-lookup"><span data-stu-id="c10ca-141">Once a user has the ability to manage permissions for a specific model, he or she can open the model to edit permissions within the model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c10ca-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c10ca-142">See Also</span></span>  
 <span data-ttu-id="c10ca-143">[Usar a segurança interna no Windows SharePoint Services para itens do servidor de relatório](use-built-in-security-in-windows-sharepoint-services-for-report-server-items.md) </span><span class="sxs-lookup"><span data-stu-id="c10ca-143">[Use Built-in Security in Windows SharePoint Services for Report Server Items](use-built-in-security-in-windows-sharepoint-services-for-report-server-items.md) </span></span>  
 <span data-ttu-id="c10ca-144">[Definir permissões para operações do servidor de relatório em um aplicativo Web do SharePoint](set-permissions-for-report-server-operations-in-a-sharepoint-web-application.md) </span><span class="sxs-lookup"><span data-stu-id="c10ca-144">[Set Permissions for Report Server Operations in a SharePoint Web Application](set-permissions-for-report-server-operations-in-a-sharepoint-web-application.md) </span></span>  
 <span data-ttu-id="c10ca-145">[Comparar funções e tarefas no Reporting Services com grupos e permissões do SharePoint](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="c10ca-145">[Compare Roles and Tasks in Reporting Services to SharePoint Groups and Permissions](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md) </span></span>  
 <span data-ttu-id="c10ca-146">[Referência à permissão de listas e sites do SharePoint para itens do servidor de relatório](sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span><span class="sxs-lookup"><span data-stu-id="c10ca-146">[SharePoint Site and List Permission Reference for Report Server Items](sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span></span>  
 [<span data-ttu-id="c10ca-147">Conceder permissões para itens do servidor de relatório em um site do SharePoint</span><span class="sxs-lookup"><span data-stu-id="c10ca-147">Granting Permissions on Report Server Items on a SharePoint Site</span></span>](granting-permissions-on-report-server-items-on-a-sharepoint-site.md)  
  
  
