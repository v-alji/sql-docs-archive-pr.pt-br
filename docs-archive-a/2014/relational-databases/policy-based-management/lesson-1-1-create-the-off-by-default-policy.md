---
title: Criar a política desativada por padrão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 98fde3c5-297c-4d95-981e-95700bbf5ccd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 16d0893c155627a41149263b5ce7b21a4a217b74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569972"
---
# <a name="create-the-off-by-default-policy"></a><span data-ttu-id="f706e-102">Criar a política desativada por padrão</span><span class="sxs-lookup"><span data-stu-id="f706e-102">Create the Off By Default Policy</span></span>
  <span data-ttu-id="f706e-103">Esta tarefa cria uma condição chamada Correio Desativado que é baseada na faceta Configuração da Área da Superfície.</span><span class="sxs-lookup"><span data-stu-id="f706e-103">This task creates a condition named Mail Off that is based on the Surface Area Configuration facet.</span></span> <span data-ttu-id="f706e-104">Então, cria uma política chamada Desativada por Padrão.</span><span class="sxs-lookup"><span data-stu-id="f706e-104">Then, it creates a policy named Off By Default.</span></span>  
  
### <a name="to-create-the-mail-off-condition"></a><span data-ttu-id="f706e-105">Para criar a condição Correio Desativado</span><span class="sxs-lookup"><span data-stu-id="f706e-105">To create the Mail Off condition</span></span>  
  
1.  <span data-ttu-id="f706e-106">Em Pesquisador de Objetos, expanda **Gerenciamento**, **Gerenciamento de Política**, **Facetas**, clique com o botão direito do mouse em **Configuração da Área da Superfície**e clique em **Nova Condição**.</span><span class="sxs-lookup"><span data-stu-id="f706e-106">In Object Explorer, expand **Management**, expand **Policy Management**, expand **Facets**, right-click **Surface Area Configuration**, and then click **New Condition**.</span></span>  
  
2.  <span data-ttu-id="f706e-107">Na caixa de diálogo **Criar Nova Condição** , na caixa **Nome** , digite **Correspondência Desativada**.</span><span class="sxs-lookup"><span data-stu-id="f706e-107">In the **Create New Condition** dialog box, in the **Name** box, type **Mail Off**.</span></span>  
  
3.  <span data-ttu-id="f706e-108">Na caixa **Faceta** , confirme se a faceta **Configuração da Área da Superfície** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="f706e-108">In the **Facet** box, confirm that **Surface Area Configuration** facet is selected.</span></span>  
  
4.  <span data-ttu-id="f706e-109">Na área **Expressão**, na caixa **Campo**, selecione **\@DatabaseMailEnabled**, na caixa **Operador**, selecione **=** e, em **Valor**, selecione **False**.</span><span class="sxs-lookup"><span data-stu-id="f706e-109">In the **Expression** area, in the **Field** box, select **\@DatabaseMailEnabled**, in the **Operator** box select **=**, and in the **Value** select **False**.</span></span>  
  
5.  <span data-ttu-id="f706e-110">Na página **Descrição** , digite uma descrição da condição e clique em **OK** para criar a condição.</span><span class="sxs-lookup"><span data-stu-id="f706e-110">On the **Description** page, type a description of the condition, and then click **OK** to create the condition.</span></span>  
  
### <a name="to-create-the-off-by-default-policy"></a><span data-ttu-id="f706e-111">Para criar a política Desativada por Padrão</span><span class="sxs-lookup"><span data-stu-id="f706e-111">To create the Off By Default policy</span></span>  
  
1.  <span data-ttu-id="f706e-112">Em Pesquisador de Objetos, clique com o botão direito do mouse em **Configuração da Área da Superfície**e clique em **Nova Política**.</span><span class="sxs-lookup"><span data-stu-id="f706e-112">In Object Explorer, right-click **Surface Area Configuration**, and then click **New Policy**.</span></span>  
  
2.  <span data-ttu-id="f706e-113">Na caixa de diálogo **Criar Nova Política** , na caixa **Nome** , digite **Desativada por Padrão**.</span><span class="sxs-lookup"><span data-stu-id="f706e-113">In the **Create New Policy** dialog box, in the **Name** box, type **Off By Default**.</span></span>  
  
3.  <span data-ttu-id="f706e-114">Deixe a caixa de seleção **Habilitada** desmarcada.</span><span class="sxs-lookup"><span data-stu-id="f706e-114">Leave the **Enabled** checkbox unchecked.</span></span> <span data-ttu-id="f706e-115">A caixa de seleção **Habilitada** se aplica às políticas automatizadas, e essa política será executada sob demanda.</span><span class="sxs-lookup"><span data-stu-id="f706e-115">The **Enabled** checkbox applies to automated policies, and this policy will be executed on demand.</span></span>  
  
4.  <span data-ttu-id="f706e-116">Na caixa de seleção **Verificar condição** , role a tela para baixo até a área **Configuração da Área da Superfície** e selecione **Correspondência Desativada** como condição de verificação.</span><span class="sxs-lookup"><span data-stu-id="f706e-116">In the **Check condition** checkbox, scroll down to the **Surface Area Configuration** area, and then select **Mail Off** as the condition to check.</span></span>  
  
5.  <span data-ttu-id="f706e-117">A caixa **Em relação aos destinos** ficará em branco porque esta é uma política com escopo no servidor.</span><span class="sxs-lookup"><span data-stu-id="f706e-117">The **Against targets** box will be blank because this is a server-scoped policy.</span></span>  
  
6.  <span data-ttu-id="f706e-118">Na caixa de seleção **Modo de Avaliação** , selecione **Sob demanda** como modo de avaliação.</span><span class="sxs-lookup"><span data-stu-id="f706e-118">In the **Evaluation Mode** checkbox, select **On demand** as the evaluation mode.</span></span>  
  
7.  <span data-ttu-id="f706e-119">Na caixa de seleção **Restrição de servidor** , selecione **Nenhuma**.</span><span class="sxs-lookup"><span data-stu-id="f706e-119">In the **Server restriction** checkbox, select **None**.</span></span>  
  
8.  <span data-ttu-id="f706e-120">Na página **Descrição** , digite uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="f706e-120">On the **Description** page, type a description of the policy.</span></span>  
  
9. <span data-ttu-id="f706e-121">Você pode fornecer um hiperlink a uma página da Web para suas políticas na área **Hiperlink de ajuda adicional** .</span><span class="sxs-lookup"><span data-stu-id="f706e-121">You can provide a hyperlink to a Web page for your policies in the **Additional help hyperlink** area.</span></span> <span data-ttu-id="f706e-122">Na caixa **Texto a ser exibido** , digite o texto que aparecerá no hiperlink.</span><span class="sxs-lookup"><span data-stu-id="f706e-122">In the **Text to display** box, type the text that will appear for the hyperlink.</span></span>  
  
10. <span data-ttu-id="f706e-123">Na caixa **Endereço** , digite um hiperlink para uma página Ajuda, como a home page do departamento de TI de sua empresa.</span><span class="sxs-lookup"><span data-stu-id="f706e-123">In the **Address** box, type a hyperlink to a Help page, such as the home page for the IT department of your company.</span></span>  
  
11. <span data-ttu-id="f706e-124">Para confirmar o endereço abrindo a página da Web, clique em **Testar Link**.</span><span class="sxs-lookup"><span data-stu-id="f706e-124">To confirm the address by opening the Web page, click **Test Link**.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="f706e-125">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="f706e-125">Next Task in Lesson</span></span>  
 [<span data-ttu-id="f706e-126">Configurar um servidor para executar a política desativada por padrão</span><span class="sxs-lookup"><span data-stu-id="f706e-126">Configure a Server to Run the Off By Default Policy</span></span>](lesson-1-2-configure-a-server-to-run-the-off-by-default-policy.md)  
  
  
