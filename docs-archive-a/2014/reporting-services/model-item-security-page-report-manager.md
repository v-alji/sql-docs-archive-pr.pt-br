---
title: Página de segurança do item de modelo (Report Manager) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.modelproperties.modelitemsecurity.f1
ms.assetid: 8c5b29ae-1f17-41f2-ab59-97899b8fb4fc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 928572437990c7f7fe1117c086c65c939aa9c999
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569185"
---
# <a name="model-item-security-page-report-manager"></a><span data-ttu-id="0fa7f-102">Página segurança de item de modelo (Gerenciador de Relatórios)</span><span class="sxs-lookup"><span data-stu-id="0fa7f-102">Model Item Security Page (Report Manager)</span></span>
  <span data-ttu-id="0fa7f-103">Use essa página para proteger partes de um modelo concedendo ou revogando permissões somente leitura em itens específicos.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-103">Use this page to secure parts of a model by granting or revoking read-only permissions on particular items.</span></span> <span data-ttu-id="0fa7f-104">A segurança de item de modelo afeta a exploração de dados ad hoc em tempo de execução e a capacidade de usar partes de um modelo publicado ao criar relatórios no Construtor de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-104">Model item security affects ad hoc data exploration at run time and the ability to use parts of a published model when creating reports in Report Builder.</span></span> <span data-ttu-id="0fa7f-105">Para usar esse recurso, você deve ter permissões de Gerenciador de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-105">To use this feature, you must have Content Manager permissions.</span></span>  
  
 <span data-ttu-id="0fa7f-106">Ela é aplicada a um modelo processado no servidor de relatório e não afeta arquivos .smdl que você edita no Designer de Modelo ou usa no Designer de Relatórios.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-106">Model item security is applied to a model that is processed on the report server and does not affect .smdl files that you edit in Model Designer or use in Report Designer.</span></span> <span data-ttu-id="0fa7f-107">Além disso, ela não afeta os usuários que têm permissão para modificar uma definição de modelo.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-107">Furthermore, it has no effect on users who have permission to modify a model definition.</span></span> <span data-ttu-id="0fa7f-108">Qualquer usuário com permissões do Gerenciador de Conteúdo ou do Publicador em um modelo pode ver partes dele, independentemente de você aplicar a segurança de item de modelo.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-108">Any user who has Content Manager or Publisher permissions on a model can see all parts of it, regardless of whether you apply model item security.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0fa7f-109">Os itens de modelo podem ter uma proteção ainda maior se você usar filtros de segurança.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-109">Model items can be further secured through the use of security filters.</span></span>  
  
 <span data-ttu-id="0fa7f-110">Você pode definir a segurança de item de modelo em entidades, pastas e campos individuais de um modelo.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-110">You can define model item security on entities, folders, and individual fields within a model.</span></span> <span data-ttu-id="0fa7f-111">Como um modelo apresenta uma grande superfície de itens de segurança, herança de permissão é criada no modelo para que um grande número de itens possa ser protegido em um número de atribuições de função relativamente pequeno.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-111">Because a model presents such a large surface of securable items, permission inheritance is built into the model so that you can secure a large number of items through a relatively small number of role assignments.</span></span> <span data-ttu-id="0fa7f-112">Herança de permissão é baseada no seguinte:</span><span class="sxs-lookup"><span data-stu-id="0fa7f-112">Permission inheritance is based on the following:</span></span>  
  
-   <span data-ttu-id="0fa7f-113">Modelo</span><span class="sxs-lookup"><span data-stu-id="0fa7f-113">Model</span></span>  
  
-   <span data-ttu-id="0fa7f-114">Nó raiz</span><span class="sxs-lookup"><span data-stu-id="0fa7f-114">Root node</span></span>  
  
-   <span data-ttu-id="0fa7f-115">Pastas ou entidades</span><span class="sxs-lookup"><span data-stu-id="0fa7f-115">Folders or entities</span></span>  
  
-   <span data-ttu-id="0fa7f-116">Campos</span><span class="sxs-lookup"><span data-stu-id="0fa7f-116">Fields</span></span>  
  
 <span data-ttu-id="0fa7f-117">Inicialmente, permissão para acessar itens de modelo é herdada por tarefas de função definidas no próprio modelo.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-117">Initially, permission to access to model items is inherited through role assignments that are set on the model itself.</span></span> <span data-ttu-id="0fa7f-118">Um usuário com permissão para exibir um modelo em uma pasta no Gerenciador de Relatórios pode exibir todos os itens no modelo.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-118">A user who has permission to view a model in a folder in Report Manager can view all of the items in the model.</span></span>  
  
 <span data-ttu-id="0fa7f-119">Se você aplicar segurança de item modelo, deve criar pelo menos uma atribuição de função no nó raiz.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-119">If you apply model item security, you must create at least one role assignment on the root node.</span></span> <span data-ttu-id="0fa7f-120">Essa atribuição de função inicial no nó raiz se torna a nova fonte de permissões herdadas.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-120">This initial role assignment on the root node becomes the new source of inherited permissions.</span></span> <span data-ttu-id="0fa7f-121">A atribuição de função no nó raiz é automaticamente herdada por todos os itens na hierarquia do modelo.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-121">The role assignment on the root node is automatically inherited by all items in the model hierarchy.</span></span>  
  
 <span data-ttu-id="0fa7f-122">Para personalizar mais permissões na exploração de dados, você pode variar as permissões nas pastas e entidades.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-122">To further customize permissions on data exploration, you can vary permissions on folders and entities.</span></span> <span data-ttu-id="0fa7f-123">Finalmente, você pode definir permissões em campos individuais.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-123">Finally, you can set permissions on individual fields.</span></span>  
  
 <span data-ttu-id="0fa7f-124">Para facilitar a manutenção das atribuições de função, só defina permissões em pastas ou entidades em vez de em campos individuais.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-124">To make role assignments easier to maintain, set permissions only on folders or entities rather than individual fields.</span></span> <span data-ttu-id="0fa7f-125">Você não pode procurar tarefas de função que você cria.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-125">You cannot search for role assignments that you create.</span></span> <span data-ttu-id="0fa7f-126">Se você definir segurança em campos específicos e quiser posteriormente atualizar as definições de segurança, terá de clicar pelo namespace do modelo para encontrar os campos protegidos.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-126">If you set security on specific fields and you want to update the security settings later, you must click through the model namespace to find the fields you secured.</span></span>  
  
 <span data-ttu-id="0fa7f-127">Para iniciar, crie uma atribuição de função no nó raiz e crie atribuições de função adicionais nas entidades e pastas.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-127">To get started, create a role assignment on the root node and then create additional role assignments on entities and folders.</span></span> <span data-ttu-id="0fa7f-128">Para desmarcar segurança do item modelo, desmarque a caixa de seleção **Proteja os itens de modelo individuais independentemente para este modelo**.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-128">To clear model item security, clear the check box for **Secure individual model items independently for this model**.</span></span> <span data-ttu-id="0fa7f-129">Ao desmarcar a caixa de seleção, as permissões iniciais herdadas do modelo serão revertidas.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-129">Clearing the check box reverts back to the initial permissions that are inherited from the model.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="0fa7f-130">Navegação</span><span class="sxs-lookup"><span data-stu-id="0fa7f-130">Navigation</span></span>  
 <span data-ttu-id="0fa7f-131">Use o procedimento a seguir para navegar para este local na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-131">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-general-properties-page-for-a-report"></a><span data-ttu-id="0fa7f-132">Para abrir a página Propriedades gerais de um relatório</span><span class="sxs-lookup"><span data-stu-id="0fa7f-132">To open the General properties page for a report</span></span>  
  
1.  <span data-ttu-id="0fa7f-133">Abra o Gerenciador de Relatórios e localize o modelo para o qual você deseja configurar a segurança de itens de modelo.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-133">Open Report Manager, and locate the model for which you want to configure security for model items.</span></span>  
  
2.  <span data-ttu-id="0fa7f-134">Focalize o modelo e clique na seta do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-134">Hover over the model, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="0fa7f-135">No menu suspenso, clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-135">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="0fa7f-136">Esse procedimento abre a página de propriedades Geral do modelo.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-136">This opens the General properties page for the model.</span></span>  
  
4.  <span data-ttu-id="0fa7f-137">Selecione a guia **Segurança do Item de Modelo** .</span><span class="sxs-lookup"><span data-stu-id="0fa7f-137">Select the **Model Item Security** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0fa7f-138">Opções</span><span class="sxs-lookup"><span data-stu-id="0fa7f-138">Options</span></span>  
 <span data-ttu-id="0fa7f-139">**Proteja os itens de modelo individuais independentemente para este modelo**</span><span class="sxs-lookup"><span data-stu-id="0fa7f-139">**Secure individual model items independently for this model**</span></span>  
 <span data-ttu-id="0fa7f-140">Clique nesta caixa de seleção para habilitar a segurança de item de modelo.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-140">Click this check box to enable model item security.</span></span>  
  
 <span data-ttu-id="0fa7f-141">**Especifique a segurança para itens de modelo individuais no modelo**</span><span class="sxs-lookup"><span data-stu-id="0fa7f-141">**Specify security for individual model items in the mode**</span></span>  
 <span data-ttu-id="0fa7f-142">Mostra todos os itens em um modelo.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-142">Shows all of the items in a model.</span></span> <span data-ttu-id="0fa7f-143">Você pode navegar no namespace do modelo para selecionar o item você quer proteger.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-143">You can navigate the model namespace to select the item you want to secure.</span></span> <span data-ttu-id="0fa7f-144">Você só pode selecionar um item de cada vez.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-144">You can only select one item at a time.</span></span> <span data-ttu-id="0fa7f-145">Crie a primeira atribuição de função no nó raiz antes de prosseguir com outras entidades e pastas.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-145">Be sure to create the first role assignment on the root node before proceeding to other entities and folders.</span></span>  
  
 <span data-ttu-id="0fa7f-146">**Herdar permissões do item pai**</span><span class="sxs-lookup"><span data-stu-id="0fa7f-146">**Inherit permissions from the parent item**</span></span>  
 <span data-ttu-id="0fa7f-147">Clique nessa opção para herdar as configurações de segurança do item pai.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-147">Click this option to inherit the security settings of the parent item.</span></span>  
  
 <span data-ttu-id="0fa7f-148">**Atribuir permissão de leitura aos seguintes usuários e grupos (separados por ponto-e-vírgula)**</span><span class="sxs-lookup"><span data-stu-id="0fa7f-148">**Assign read permission to the following users and groups (semi-colon separated)**</span></span>  
 <span data-ttu-id="0fa7f-149">Clique nessa opção para especificar o usuário ou a conta de grupo para os quais você está definindo acesso.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-149">Click this option to specify the user or group account for which you are defining access.</span></span> <span data-ttu-id="0fa7f-150">Se você estiver usando segurança padrão, as contas de usuário e grupo serão contas do domínio Windows.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-150">If you are using default security, the user and group accounts are Windows domain accounts.</span></span> <span data-ttu-id="0fa7f-151">Especifique as contas neste formato: \* \<domain> \\<conta \> \*.</span><span class="sxs-lookup"><span data-stu-id="0fa7f-151">Specify the accounts in this format: *\<domain>\\<account\>*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fa7f-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0fa7f-152">See Also</span></span>  
 [<span data-ttu-id="0fa7f-153">Servidor de Relatório na ajuda F1 do Management Studio</span><span class="sxs-lookup"><span data-stu-id="0fa7f-153">Report Server in Management Studio F1 Help</span></span>](tools/report-server-in-management-studio-f1-help.md)  
  
  
