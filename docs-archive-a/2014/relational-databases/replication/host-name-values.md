---
title: Valores HOST_NAME | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.hostnamevalue.f1
ms.assetid: 21548f08-2910-4a55-baac-b911ba9afaf1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 67d01df05c8d56fd435eb0ee1b42ba2da6a312ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569888"
---
# <a name="host_name-values"></a><span data-ttu-id="fd480-102">Valores HOST_NAME</span><span class="sxs-lookup"><span data-stu-id="fd480-102">HOST_NAME Values</span></span>
  <span data-ttu-id="fd480-103">Asp ublicações de mesclagem com filtros com parâmetros usam a função SUSER_SNAME() e/ou a função HOST_NAME() para filtrar dados.</span><span class="sxs-lookup"><span data-stu-id="fd480-103">Merge publications with parameterized filters use the SUSER_SNAME() function and/or the HOST_NAME() function to filter data.</span></span> <span data-ttu-id="fd480-104">A função é especificada no Assistente para Nova Publicação ou na caixa de diálogo **Propriedades de Publicação** .</span><span class="sxs-lookup"><span data-stu-id="fd480-104">The function is specified in the New Publication Wizard or the **Publication Properties** dialog box.</span></span>  
  
 <span data-ttu-id="fd480-105">Por padrão, a função HOST_NAME() retorna o nome do computador que conecta ao Publicador.</span><span class="sxs-lookup"><span data-stu-id="fd480-105">By default, the HOST_NAME() function returns the name of the computer connecting to the Publisher.</span></span> <span data-ttu-id="fd480-106">É comum substituir esse valor, ao usar filtros com parâmetros, fornecendo um valor nessa página do assistente.</span><span class="sxs-lookup"><span data-stu-id="fd480-106">When using parameterized filters, it is common to override this value by supplying a value on this page of the wizard.</span></span> <span data-ttu-id="fd480-107">Uma função HOST_NAME() retorna o valor que você especifica em lugar do nome do computador.</span><span class="sxs-lookup"><span data-stu-id="fd480-107">The HOST_NAME() function then returns the value you specify rather than the name of the computer.</span></span> <span data-ttu-id="fd480-108">Para mais informações, consulte a seção “Substituindo o valor do HOST_NAME()” de [Filtros de linha com parâmetros](merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="fd480-108">For more information, see the "Overriding the HOST_NAME() Value" section of [Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fd480-109">Se substituir HOST_NAME(), todas as chamadas para a função HOST_NAME() retornarão o valor que você especificou.</span><span class="sxs-lookup"><span data-stu-id="fd480-109">If you override HOST_NAME(), all calls to the HOST_NAME() function will return the value you specify.</span></span> <span data-ttu-id="fd480-110">Assegure-se de que outros aplicativos não estão dependendo de que HOST_NAME() retorne o nome do computador.</span><span class="sxs-lookup"><span data-stu-id="fd480-110">Ensure that other applications are not depending on HOST_NAME() returning the computer name.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fd480-111">Opções</span><span class="sxs-lookup"><span data-stu-id="fd480-111">Options</span></span>  
 <span data-ttu-id="fd480-112">**Propriedades da assinatura**</span><span class="sxs-lookup"><span data-stu-id="fd480-112">**Subscription properties**</span></span>  
 <span data-ttu-id="fd480-113">Insira um valor para cada Assinante na coluna **Valor de HOST_NAME** ou aceite o padrão, que é o nome do computador do Assinante.</span><span class="sxs-lookup"><span data-stu-id="fd480-113">Enter a value for each Subscriber in the **HOST_NAME Value** column or accept the default, which is the name of the Subscriber computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd480-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="fd480-114">See Also</span></span>  
 <span data-ttu-id="fd480-115">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="fd480-115">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="fd480-116">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="fd480-116">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="fd480-117">[Exibir e modificar propriedades de assinatura pull](view-and-modify-pull-subscription-properties.md) </span><span class="sxs-lookup"><span data-stu-id="fd480-117">[View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md) </span></span>  
 <span data-ttu-id="fd480-118">[Exibir e modificar propriedades de assinatura push](view-and-modify-push-subscription-properties.md) </span><span class="sxs-lookup"><span data-stu-id="fd480-118">[View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) </span></span>  
 <span data-ttu-id="fd480-119">[HOST_NAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/host-name-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fd480-119">[HOST_NAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/host-name-transact-sql) </span></span>  
 [<span data-ttu-id="fd480-120">Assinar publicações</span><span class="sxs-lookup"><span data-stu-id="fd480-120">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
