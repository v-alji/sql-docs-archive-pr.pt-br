---
title: Adicionar várias condições a uma regra de negócios (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], multiple conditions
ms.assetid: 5f0f6958-6cf2-444b-bdcd-05b887637a0b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c62b8dfa4f459958d12bd384b85aa74bef382b21
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575898"
---
# <a name="add-multiple-conditions-to-a-business-rule-master-data-services"></a><span data-ttu-id="f6a95-102">Adicionar várias condições a uma regra de negócio (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f6a95-102">Add Multiple Conditions to a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="f6a95-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], adicione várias condições **AND** ou **OR** a uma regra de negócio quando desejar uma regra mais complexa.</span><span class="sxs-lookup"><span data-stu-id="f6a95-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], add multiple **AND** or **OR** conditions to a business rule when you want a more complex rule.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f6a95-104">Se você criar uma regra de negócio que usa o operador **OR** , considere a criação de uma regra separada para cada instrução condicional que possa ser avaliada independentemente.</span><span class="sxs-lookup"><span data-stu-id="f6a95-104">If you create a business rule that uses the **OR** operator, consider creating a separate rule for each conditional statement that can be evaluated independently.</span></span> <span data-ttu-id="f6a95-105">É possível excluir regras conforme necessário, para garantir mais flexibilidade e uma solução de problemas mais fácil.</span><span class="sxs-lookup"><span data-stu-id="f6a95-105">You can then exclude rules as needed, providing more flexibility and easier troubleshooting.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f6a95-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f6a95-106">Prerequisites</span></span>  
 <span data-ttu-id="f6a95-107">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="f6a95-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="f6a95-108">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="f6a95-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="f6a95-109">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="f6a95-109">You must be a model administrator.</span></span> <span data-ttu-id="f6a95-110">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f6a95-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="f6a95-111">Uma regra de negócios deve existir.</span><span class="sxs-lookup"><span data-stu-id="f6a95-111">A business rule must exist.</span></span> <span data-ttu-id="f6a95-112">Para obter mais informações, consulte [Criar e publicar uma regra de negócio &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f6a95-112">For more information, see [Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span></span>  
  
### <a name="to-add-multiple-conditions-to-a-business-rule"></a><span data-ttu-id="f6a95-113">Para acrescentar várias condições a uma regra de negócio</span><span class="sxs-lookup"><span data-stu-id="f6a95-113">To add multiple conditions to a business rule</span></span>  
  
1.  <span data-ttu-id="f6a95-114">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="f6a95-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="f6a95-115">Na barra de menus, aponte para **Gerenciar** e clique em **Regras de Negócios**.</span><span class="sxs-lookup"><span data-stu-id="f6a95-115">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="f6a95-116">Na página **Manutenção de Regra de Negócio** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="f6a95-116">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="f6a95-117">Na lista **Entidade** , selecione uma entidade.</span><span class="sxs-lookup"><span data-stu-id="f6a95-117">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="f6a95-118">Na lista **tipo de membro** , selecione um tipo de membro.</span><span class="sxs-lookup"><span data-stu-id="f6a95-118">From the **Member Type** list, select a type of member.</span></span>  
  
6.  <span data-ttu-id="f6a95-119">Na lista **Atributo** , selecione um atributo ou deixe o valor padrão **Todos**.</span><span class="sxs-lookup"><span data-stu-id="f6a95-119">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="f6a95-120">Clique na linha da regra de negócio que deseja editar.</span><span class="sxs-lookup"><span data-stu-id="f6a95-120">Click the row for the business rule you want to edit.</span></span>  
  
8.  <span data-ttu-id="f6a95-121">Clique em **Editar regra de negócio selecionada**.</span><span class="sxs-lookup"><span data-stu-id="f6a95-121">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="f6a95-122">No painel **componentes** , expanda o nó **operadores lógicos** .</span><span class="sxs-lookup"><span data-stu-id="f6a95-122">In the **Components** pane, expand the **Logical Operators** node.</span></span>  
  
10. <span data-ttu-id="f6a95-123">Clique **AND** em e **ou em e arraste** -o para o painel de **If** **e** o rótulo.</span><span class="sxs-lookup"><span data-stu-id="f6a95-123">Click **AND** or **OR** and drag it to the **IF** pane's **AND** label.</span></span>  
  
11. <span data-ttu-id="f6a95-124">No painel **Componentes** , expanda o nó **Condições** .</span><span class="sxs-lookup"><span data-stu-id="f6a95-124">In the **Components** pane, expand the **Conditions** node.</span></span>  
  
12. <span data-ttu-id="f6a95-125">Clique em uma condição e arraste-a para **se** painel, para o **e** ou **ou** para o rótulo da etapa 10.</span><span class="sxs-lookup"><span data-stu-id="f6a95-125">Click a condition and drag it to **IF** pane, to the **AND** or **OR** label from step 10.</span></span>  
  
13. <span data-ttu-id="f6a95-126">No painel **atributos** , clique em um atributo e arraste-o para o rótulo de **atributo selecionar** do painel de **condição de edição** .</span><span class="sxs-lookup"><span data-stu-id="f6a95-126">In the **Attributes** pane, click an attribute and drag it to the **Edit Condition** pane's **Select attribute** label.</span></span>  
  
14. <span data-ttu-id="f6a95-127">No painel **Editar condição** , preencha todos os campos obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="f6a95-127">In the **Edit Condition** pane, complete any required fields.</span></span>  
  
15. <span data-ttu-id="f6a95-128">No painel **Editar Condição** , clique em **Salvar item**.</span><span class="sxs-lookup"><span data-stu-id="f6a95-128">In the **Edit Condition** pane, click **Save item**.</span></span>  
  
16. <span data-ttu-id="f6a95-129">Opcionalmente, para adicionar mais condições, no painel **componentes** , arraste **e** ou **ou** para qualquer **e** **ou ou no painel** **If** .</span><span class="sxs-lookup"><span data-stu-id="f6a95-129">Optionally, to add more conditions, from the **Components** pane, drag **AND** or **OR** to any **AND** or **OR** in the **IF** pane.</span></span> <span data-ttu-id="f6a95-130">Então siga as etapas 13 a 15.</span><span class="sxs-lookup"><span data-stu-id="f6a95-130">Then follow steps 13-15.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="f6a95-131">Para excluir uma condição, clique no nome da condição e, no painel **Editar condição** , clique em **Excluir item**.</span><span class="sxs-lookup"><span data-stu-id="f6a95-131">To delete a condition, click the name of the condition and in the **Edit Condition** pane, click **Delete item**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6a95-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f6a95-132">See Also</span></span>  
 <span data-ttu-id="f6a95-133">[Regras de negócio &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="f6a95-133">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 <span data-ttu-id="f6a95-134">[Alterar o nome de uma regra de negócio &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="f6a95-134">[Change a Business Rule Name &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span></span>  
 [<span data-ttu-id="f6a95-135">Configurar regras de negócio para enviar notificações &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f6a95-135">Configure Business Rules to Send Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md)  
  
  
