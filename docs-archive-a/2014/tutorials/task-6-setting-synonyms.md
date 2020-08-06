---
title: 'Tarefa 6: definindo sinônimos | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: b7d35ee9-d1c9-41d9-bbc5-0ca7db93e54d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bde0c0ec7f230ba2325aa01328b191fd8fd67fa6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568951"
---
# <a name="task-6-setting-synonyms"></a><span data-ttu-id="2f754-102">Tarefa 6: Definindo sinônimos</span><span class="sxs-lookup"><span data-stu-id="2f754-102">Task 6: Setting Synonyms</span></span>
  <span data-ttu-id="2f754-103">Nesta tarefa, você define dois valores de domínio, **USA** e **United States**, do domínio **Country** como sinônimos, sendo **United States** o valor principal.</span><span class="sxs-lookup"><span data-stu-id="2f754-103">In this task, you set two domain values, **USA** and **United States**, of the **Country** domain as synonyms with **United States** as the leading value.</span></span> <span data-ttu-id="2f754-104">Como a opção **Usar Valores Principais** foi selecionada durante a criação do domínio **Country** , todos os valores **USA** do domínio **Country** serão gerados como **United States** (porque United States é o valor principal).</span><span class="sxs-lookup"><span data-stu-id="2f754-104">Since the **Use Leading Values** option was selected when creating the **Country** domain, any **USA** values for the **Country** domain will be output as **United States** (as United States is the leading value).</span></span> <span data-ttu-id="2f754-105">Consulte [Alterar Valores de Domínio](https://msdn.microsoft.com/library/hh510408.aspx) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="2f754-105">See [Change Domain Values](https://msdn.microsoft.com/library/hh510408.aspx) for more details.</span></span>

1.  <span data-ttu-id="2f754-106">Selecione **Country** na lista de domínios.</span><span class="sxs-lookup"><span data-stu-id="2f754-106">Select **Country** from the list of domains.</span></span>

2.  <span data-ttu-id="2f754-107">Alterne para a guia **Valores de Domínio** .</span><span class="sxs-lookup"><span data-stu-id="2f754-107">Switch to the **Domain Values** tab.</span></span>

3.  <span data-ttu-id="2f754-108">Clique no botão **Adicionar novo valor de domínio** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="2f754-108">Click **Add new domain value** button on the toolbar.</span></span>

4.  <span data-ttu-id="2f754-109">Digite **USA** como valor e pressione **ENTER**.</span><span class="sxs-lookup"><span data-stu-id="2f754-109">Type **USA** for the value and press **ENTER**.</span></span>

5.  <span data-ttu-id="2f754-110">Selecione vários valores **United States** e **USA** usando as teclas CTRL ou SHIFT, clique com o botão direito do mouse nos itens selecionados e clique em **Definir como Sinônimo**.</span><span class="sxs-lookup"><span data-stu-id="2f754-110">Multiselect **United States** and **USA** using CTRL or SHIFT keys, right-click the selected items, and then click **Set as Synonyms**.</span></span> <span data-ttu-id="2f754-111">O DQS agrupará esses valores e designará um deles como o valor principal que substituirá os outros.</span><span class="sxs-lookup"><span data-stu-id="2f754-111">DQS groups these values and designate one of the values as the leading value that the other values are replaced with.</span></span>

     <span data-ttu-id="2f754-112">![Menu Definir como Sinônimos](../../2014/tutorials/media/et-settingsynonyms-01.jpg "Menu Definir como Sinônimos")</span><span class="sxs-lookup"><span data-stu-id="2f754-112">![Set as Synonyms Menu](../../2014/tutorials/media/et-settingsynonyms-01.jpg "Set as Synonyms Menu")</span></span>

6.  <span data-ttu-id="2f754-113">Observe que **United States** está definido como valor principal.</span><span class="sxs-lookup"><span data-stu-id="2f754-113">Notice that **United States** is set as the leading value.</span></span> <span data-ttu-id="2f754-114">Se você quiser que USA seja o valor principal, clique com o botão direito do mouse em USA e selecione a opção **Definir como Principal** .</span><span class="sxs-lookup"><span data-stu-id="2f754-114">If you want USA to be the leading value, you can right-click on USA and select **Set as Leading** option.</span></span> <span data-ttu-id="2f754-115">Neste tutorial, usamos **United States** como valor principal.</span><span class="sxs-lookup"><span data-stu-id="2f754-115">For this tutorial, we use **United States** as the leading value.</span></span>

     <span data-ttu-id="2f754-116">![Estados Unidos e EUA como sinônimos](../../2014/tutorials/media/et-settingsynonyms-02.jpg "Estados Unidos e EUA como sinônimos")</span><span class="sxs-lookup"><span data-stu-id="2f754-116">![United States and USA as Synonyms](../../2014/tutorials/media/et-settingsynonyms-02.jpg "United States and USA as Synonyms")</span></span>

## <a name="next-step"></a><span data-ttu-id="2f754-117">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="2f754-117">Next Step</span></span>
 [<span data-ttu-id="2f754-118">Tarefa 7: Criando uma domínio composto</span><span class="sxs-lookup"><span data-stu-id="2f754-118">Task 7: Creating a Composite Domain</span></span>](../../2014/tutorials/task-7-creating-a-composite-domain.md)


