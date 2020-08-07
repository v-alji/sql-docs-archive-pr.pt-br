---
title: Gerar automaticamente valores de atributo de código (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 19b354ee-2906-4cc7-ba2f-32b4543bddcf
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 6c442f37ffe322985ba55b29b2c4cd539b8a3e05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581994"
---
# <a name="automatically-generate-code-attribute-values-master-data-services"></a><span data-ttu-id="13e88-102">Gerar automaticamente valores de atributo de código (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="13e88-102">Automatically Generate Code Attribute Values (Master Data Services)</span></span>
  <span data-ttu-id="13e88-103">No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], gera automaticamente valores para o atributo Code de uma entidade quando você deseja atribuir um inteiro automaticamente ao valor de código toda vez que um novo membro é criado.</span><span class="sxs-lookup"><span data-stu-id="13e88-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], automatically generate values for an entity's Code attribute when you want an integer to be automatically assigned to the Code value each time a new member is created.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="13e88-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="13e88-104">Prerequisites</span></span>  
 <span data-ttu-id="13e88-105">Para executar esse procedimento:</span><span class="sxs-lookup"><span data-stu-id="13e88-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="13e88-106">Você deve ter permissão para acessar a área funcional **Administração do sistema** .</span><span class="sxs-lookup"><span data-stu-id="13e88-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="13e88-107">Você deve ser um administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="13e88-107">You must be a model administrator.</span></span> <span data-ttu-id="13e88-108">Para obter mais informações, consulte [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="13e88-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="13e88-109">A entidade deve existir.</span><span class="sxs-lookup"><span data-stu-id="13e88-109">The entity must exist.</span></span> <span data-ttu-id="13e88-110">Para obter mais informações, consulte [criar uma entidade &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="13e88-110">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-automatically-generate-code-values"></a><span data-ttu-id="13e88-111">Para gerar valores de código automaticamente.</span><span class="sxs-lookup"><span data-stu-id="13e88-111">To automatically generate Code values</span></span>  
  
1.  <span data-ttu-id="13e88-112">No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="13e88-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="13e88-113">Na página **Gerenciador de modelos** , na barra de menus, aponte para **gerenciar** e clique em **entidades**.</span><span class="sxs-lookup"><span data-stu-id="13e88-113">On the **Model Explorer** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="13e88-114">Na página **Manutenção da Entidade** , na lista **Modelo** , selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="13e88-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="13e88-115">Selecione a linha da entidade para a qual você deseja gerar códigos.</span><span class="sxs-lookup"><span data-stu-id="13e88-115">Select the row for the entity that you want to generate codes for.</span></span>  
  
5.  <span data-ttu-id="13e88-116">Clique em **Editar entidade selecionada**.</span><span class="sxs-lookup"><span data-stu-id="13e88-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="13e88-117">Marque a caixa de seleção **Criar valores de códigos automaticamente** .</span><span class="sxs-lookup"><span data-stu-id="13e88-117">Select the **Create Code values automatically** check box.</span></span>  
  
7.  <span data-ttu-id="13e88-118">Na caixa **Iniciar com** , digite um número para começar a incrementar.</span><span class="sxs-lookup"><span data-stu-id="13e88-118">In the **Start with** box, type a number to begin incrementing.</span></span> <span data-ttu-id="13e88-119">Se os membros já existirem, o Código será definido com base no valor existente mais alto.</span><span class="sxs-lookup"><span data-stu-id="13e88-119">If members already exist, the Code will be set based on the highest existing value.</span></span> <span data-ttu-id="13e88-120">Por exemplo, se o valor de código existente mais alto for 299, o valor de código do próximo membro será definido como 300.</span><span class="sxs-lookup"><span data-stu-id="13e88-120">For example, if the highest existing Code value is 299, the next member's Code value will be set to 300.</span></span>  
  
8.  <span data-ttu-id="13e88-121">Clique em **Salvar entidade**.</span><span class="sxs-lookup"><span data-stu-id="13e88-121">Click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13e88-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="13e88-122">See Also</span></span>  
 <span data-ttu-id="13e88-123">[Criação de código automática &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="13e88-123">[Automatic Code Creation &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span></span>  
 [<span data-ttu-id="13e88-124">Gerar automaticamente valores de atributo diferentes de código &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="13e88-124">Automatically Generate Attribute Values Other Than Code &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/automatically-generate-attribute-values-other-than-code-master-data-services.md)  
  
  
