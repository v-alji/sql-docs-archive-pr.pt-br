---
title: 'Tarefa 4: definindo regras de domínio | Microsoft Docs'
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 3a7162ba-cf2f-481f-830d-bb6a02823827
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 42bdbd0228fdd3515f68ce830581f445242768e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569743"
---
# <a name="task-4-setting-domain-rules"></a><span data-ttu-id="5adef-102">Tarefa 4: Definindo regras de domínio</span><span class="sxs-lookup"><span data-stu-id="5adef-102">Task 4: Setting Domain Rules</span></span>
  <span data-ttu-id="5adef-103">Nesta tarefa, você cria uma regra para o domínio de **email de contato** para verificar se o endereço de email termina com \*\* \@ Adventure-Works.com\*\*.</span><span class="sxs-lookup"><span data-stu-id="5adef-103">In this task, you create a rule for the **Contact Email** domain to verify if the email address ends with **\@adventure-works.com**.</span></span> <span data-ttu-id="5adef-104">Consulte o tópico [criando uma regra de domínio](https://msdn.microsoft.com/library/hh510397.aspx) para obter mais detalhes sobre a página.</span><span class="sxs-lookup"><span data-stu-id="5adef-104">See [Creating a Domain Rule](https://msdn.microsoft.com/library/hh510397.aspx) topic for more details on the page.</span></span>  
  
1.  <span data-ttu-id="5adef-105">Clique em **email de contato** na lista de **domínios**.</span><span class="sxs-lookup"><span data-stu-id="5adef-105">Click **Contact Email** in the **Domain list**.</span></span>  
  
2.  <span data-ttu-id="5adef-106">Alterne para a guia **regras de domínio** no painel direito.</span><span class="sxs-lookup"><span data-stu-id="5adef-106">Switch to the **Domain Rules** tab in the right pane.</span></span>  
  
     <span data-ttu-id="5adef-107">![Botão de barra de ferramentas Adicionar uma Nova Regra de Domínio](../../2014/tutorials/media/et-settingdomainrules-01.jpg "Botão de barra de ferramentas Adicionar uma Nova Regra de Domínio")</span><span class="sxs-lookup"><span data-stu-id="5adef-107">![Add a New Domain Rule Toolbar Button](../../2014/tutorials/media/et-settingdomainrules-01.jpg "Add a New Domain Rule Toolbar Button")</span></span>  
  
3.  <span data-ttu-id="5adef-108">No painel direito, clique no botão **Adicionar uma nova regra de domínio** na barra de ferramentas (consulte a imagem) para adicionar uma regra.</span><span class="sxs-lookup"><span data-stu-id="5adef-108">In the right pane, click **Add a new domain rule** button on the toolbar (see the image) to add a rule.</span></span>  
  
4.  <span data-ttu-id="5adef-109">Digite **validação de email** para o **nome da regra** e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="5adef-109">Type **Email Validation** for the **rule name** and press **ENTER**.</span></span> <span data-ttu-id="5adef-110">A caixa de seleção **ativa** deve ser marcada por padrão.</span><span class="sxs-lookup"><span data-stu-id="5adef-110">The **Active** check box should be checked by default.</span></span> <span data-ttu-id="5adef-111">Esse controle permite a você desativar temporariamente uma regra.</span><span class="sxs-lookup"><span data-stu-id="5adef-111">This control allows you to deactivate a rule temporarily.</span></span>  
  
5.  <span data-ttu-id="5adef-112">No painel **criar uma regra** , clique na **seta para baixo**e selecione **valor termina com**.</span><span class="sxs-lookup"><span data-stu-id="5adef-112">In the **Build a Rule** pane, click **down arrow**, and select **Value ends with**.</span></span>  
  
6.  <span data-ttu-id="5adef-113">Digite \*\* \@ Adventure-Works.com\*\* na caixa de texto e pressione **Tab**.</span><span class="sxs-lookup"><span data-stu-id="5adef-113">Type **\@adventure-works.com** in the text box and press **TAB**.</span></span> <span data-ttu-id="5adef-114">Você pode adicionar mais condições clicando em **Adicionar uma nova condição ao** botão da barra de ferramentas da cláusula selecionada no painel **criar uma regra** .</span><span class="sxs-lookup"><span data-stu-id="5adef-114">You can add more conditions by clicking **Add a new condition to the selected clause** toolbar button in the **Build a Rule** pane.</span></span>  
  
     <span data-ttu-id="5adef-115">![Regra Validação de Email](../../2014/tutorials/media/et-settingdomainrules-02.jpg "Regra Validação de Email")</span><span class="sxs-lookup"><span data-stu-id="5adef-115">![Email Validation Rule](../../2014/tutorials/media/et-settingdomainrules-02.jpg "Email Validation Rule")</span></span>  
  
7.  <span data-ttu-id="5adef-116">Clique no botão **executar a regra de domínio selecionada no dados de teste** na barra de ferramentas no painel direito para testar a regra em relação aos dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="5adef-116">Click **Run the selected domain rule on test data** button on the toolbar in the right pane to test the rule against sample data.</span></span>  
  
     <span data-ttu-id="5adef-117">![Executar a Regra de Domínio em botão de barra de ferramentas Testar Dados](../../2014/tutorials/media/et-settingdomainrules-03.jpg "Executar a Regra de Domínio em botão de barra de ferramentas Testar Dados")</span><span class="sxs-lookup"><span data-stu-id="5adef-117">![Run the Domain Rule on Test Data Toolbar Button](../../2014/tutorials/media/et-settingdomainrules-03.jpg "Run the Domain Rule on Test Data Toolbar Button")</span></span>  
  
8.  <span data-ttu-id="5adef-118">Na caixa de diálogo **testar regra de domínio** , clique em **adiciona um novo termo de teste para o botão regra de domínio** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="5adef-118">In the **Test Domain Rule** dialog box, click **Adds a new testing term for the domain rule** button on the toolbar.</span></span>  
  
     <span data-ttu-id="5adef-119">![Caixa de diálogo de regra Testar Domínio](../../2014/tutorials/media/et-settingdomainrules-04.jpg "Caixa de diálogo de regra Testar Domínio")</span><span class="sxs-lookup"><span data-stu-id="5adef-119">![Test Domain Rule Dialog Box](../../2014/tutorials/media/et-settingdomainrules-04.jpg "Test Domain Rule Dialog Box")</span></span>  
  
9. <span data-ttu-id="5adef-120">Digite **frank7 \@ Adventure-Works.com** (um valor válido) na coluna **email de contato** .</span><span class="sxs-lookup"><span data-stu-id="5adef-120">Type **frank7\@adventure-works.com** (a valid value) in the **Contact Email** column.</span></span>  
  
10. <span data-ttu-id="5adef-121">Repita as duas etapas anteriores para adicionar **joe2 \@ Adventure-Work.com** (um valor inválido sem ' ').</span><span class="sxs-lookup"><span data-stu-id="5adef-121">Repeat previous two steps to add **joe2\@adventure-work.com** (an invalid value with no 's').</span></span>  
  
11. <span data-ttu-id="5adef-122">Clique no botão último (**teste a regra de domínio em todos os termos**) na barra de ferramentas para testar os dados de entrada em relação à regra.</span><span class="sxs-lookup"><span data-stu-id="5adef-122">Click the last button (**Test the domain rule on all the terms**) on the toolbar to test the input data against the rule.</span></span>  
  
     <span data-ttu-id="5adef-123">![Testar a Regra de Domínio em botão de barra de ferramentas Todos os Termos](../../2014/tutorials/media/et-settingdomainrules-05.jpg "Testar a Regra de Domínio em botão de barra de ferramentas Todos os Termos")</span><span class="sxs-lookup"><span data-stu-id="5adef-123">![Test the Domain Rule on All Terms Toolbar Button](../../2014/tutorials/media/et-settingdomainrules-05.jpg "Test the Domain Rule on All Terms Toolbar Button")</span></span>  
  
12. <span data-ttu-id="5adef-124">Observe que a primeira entrada será mostrada como um item válido e a segunda como um item inválido.</span><span class="sxs-lookup"><span data-stu-id="5adef-124">Notice that the first entry is shown as a valid item and the second one as an invalid item.</span></span>  
  
     <span data-ttu-id="5adef-125">![Resultados da Regra Testar Domínio](../../2014/tutorials/media/et-settingdomainrules-06.jpg "Resultados da Regra Testar Domínio")</span><span class="sxs-lookup"><span data-stu-id="5adef-125">![Test Domain Rule Results](../../2014/tutorials/media/et-settingdomainrules-06.jpg "Test Domain Rule Results")</span></span>  
  
13. <span data-ttu-id="5adef-126">Clique em **fechar** para fechar a caixa de diálogo **testar regra de domínio** .</span><span class="sxs-lookup"><span data-stu-id="5adef-126">Click **Close** to close the **Test Domain Rule** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="5adef-127">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="5adef-127">Next Step</span></span>  
 [<span data-ttu-id="5adef-128">Tarefa 5: Definindo relações baseadas em termos</span><span class="sxs-lookup"><span data-stu-id="5adef-128">Task 5: Setting Term Based Relationships</span></span>](../../2014/tutorials/task-5-setting-term-based-relationships.md)  
  
  
