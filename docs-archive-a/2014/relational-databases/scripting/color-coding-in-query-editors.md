---
title: Codificação por cores no Editor de Consultas
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Query Editor [SQL Server Management Studio], color coding
- color coding [Query Editor]
ms.assetid: 802882dc-c997-4e3f-8a01-994bb43169ae
author: rothja
ms.author: jroth
ms.openlocfilehash: f23b37cec051b52082cdb310a134a4603423b8c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572452"
---
# <a name="color-coding-in-query-editors"></a><span data-ttu-id="a49a7-102">Codificação por cores no Editor de Consultas</span><span class="sxs-lookup"><span data-stu-id="a49a7-102">Color Coding in Query Editors</span></span>
  <span data-ttu-id="a49a7-103">É atribuída uma categoria ao texto inserido nos editores de códigos; cada categoria é identificada por uma cor.</span><span class="sxs-lookup"><span data-stu-id="a49a7-103">The text entered in the code editors is assigned a category; each category is identified by a color.</span></span> <span data-ttu-id="a49a7-104">As cores ajudam você a localizar rapidamente o texto no código.</span><span class="sxs-lookup"><span data-stu-id="a49a7-104">The colors help you quickly find text in your code.</span></span> <span data-ttu-id="a49a7-105">Por exemplo, os comentários se destacam em verde-escuro.</span><span class="sxs-lookup"><span data-stu-id="a49a7-105">For example, comments stand out in dark green.</span></span> <span data-ttu-id="a49a7-106">A tabela a seguir lista as cores mais comuns.</span><span class="sxs-lookup"><span data-stu-id="a49a7-106">The following table lists the most common colors.</span></span> <span data-ttu-id="a49a7-107">Você pode exibir a lista completa de cores e suas categorias, e configurar um esquema de cores personalizado usando o menu **Ferramentas**, **Opções** .</span><span class="sxs-lookup"><span data-stu-id="a49a7-107">You can view the whole list of colors and their categories, and configure a custom color scheme by using the **Tools**, **Options** menu.</span></span> <span data-ttu-id="a49a7-108">Para obter mais informações sobre como alterar as cores padrão, veja [Alterar cor, tamanho e estilo da fonte](change-font-color-size-and-style.md).</span><span class="sxs-lookup"><span data-stu-id="a49a7-108">For more information about how to change the default colors, see [Change Font Color, Size, and Style](change-font-color-size-and-style.md).</span></span>  
  
## <a name="default-code-colors"></a><span data-ttu-id="a49a7-109">Cores de código padrão</span><span class="sxs-lookup"><span data-stu-id="a49a7-109">Default Code Colors</span></span>  
  
|<span data-ttu-id="a49a7-110">Color</span><span class="sxs-lookup"><span data-stu-id="a49a7-110">Color</span></span>|<span data-ttu-id="a49a7-111">Categoria</span><span class="sxs-lookup"><span data-stu-id="a49a7-111">Category</span></span>|  
|-----------|--------------|  
|<span data-ttu-id="a49a7-112">Vermelho</span><span class="sxs-lookup"><span data-stu-id="a49a7-112">Red</span></span>|<span data-ttu-id="a49a7-113">Cadeia de caracteres SQL</span><span class="sxs-lookup"><span data-stu-id="a49a7-113">SQL string</span></span>|  
|<span data-ttu-id="a49a7-114">Verde-escuro</span><span class="sxs-lookup"><span data-stu-id="a49a7-114">Dark green</span></span>|<span data-ttu-id="a49a7-115">Comentário</span><span class="sxs-lookup"><span data-stu-id="a49a7-115">Comment</span></span>|  
|<span data-ttu-id="a49a7-116">Preto sobre fundo prateado</span><span class="sxs-lookup"><span data-stu-id="a49a7-116">Black on silver background</span></span>|<span data-ttu-id="a49a7-117">Comando SQLCMD</span><span class="sxs-lookup"><span data-stu-id="a49a7-117">SQLCMD command</span></span>|  
|<span data-ttu-id="a49a7-118">Magenta</span><span class="sxs-lookup"><span data-stu-id="a49a7-118">Magenta</span></span>|<span data-ttu-id="a49a7-119">Função do sistema</span><span class="sxs-lookup"><span data-stu-id="a49a7-119">System function</span></span>|  
|<span data-ttu-id="a49a7-120">Verde</span><span class="sxs-lookup"><span data-stu-id="a49a7-120">Green</span></span>|<span data-ttu-id="a49a7-121">Tabela, exibição ou função com valor de tabela do sistema.</span><span class="sxs-lookup"><span data-stu-id="a49a7-121">System table, view, or table-valued function.</span></span> <span data-ttu-id="a49a7-122">Além disso, esquemas do sistema, sys e INFORMATION_SCHEMA.</span><span class="sxs-lookup"><span data-stu-id="a49a7-122">Also, the system schemas sys and INFORMATION_SCHEMA.</span></span>|  
|<span data-ttu-id="a49a7-123">Azul</span><span class="sxs-lookup"><span data-stu-id="a49a7-123">Blue</span></span>|<span data-ttu-id="a49a7-124">Palavra-chave</span><span class="sxs-lookup"><span data-stu-id="a49a7-124">Keyword</span></span>|  
|<span data-ttu-id="a49a7-125">Azul-petróleo</span><span class="sxs-lookup"><span data-stu-id="a49a7-125">Teal</span></span>|<span data-ttu-id="a49a7-126">Números de linha ou parâmetro de modelo</span><span class="sxs-lookup"><span data-stu-id="a49a7-126">Line numbers or template parameter</span></span>|  
|<span data-ttu-id="a49a7-127">Castanho</span><span class="sxs-lookup"><span data-stu-id="a49a7-127">Maroon</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a49a7-128">procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="a49a7-128">stored procedure</span></span>|  
|<span data-ttu-id="a49a7-129">Cinza escuro</span><span class="sxs-lookup"><span data-stu-id="a49a7-129">Dark gray</span></span>|<span data-ttu-id="a49a7-130">Operadores</span><span class="sxs-lookup"><span data-stu-id="a49a7-130">Operators</span></span>|  
  
## <a name="status-bar"></a><span data-ttu-id="a49a7-131">Barra de Status</span><span class="sxs-lookup"><span data-stu-id="a49a7-131">Status Bar</span></span>  
 <span data-ttu-id="a49a7-132">Você pode configurar servidores registrados ou servidores [!INCLUDE[ssDE](../../includes/ssde-md.md)] em Pesquisador de Objetos para ter cores diferentes na barra de status do Editor de Consulta [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a49a7-132">You can configure registered servers or [!INCLUDE[ssDE](../../includes/ssde-md.md)] servers in Object Explorer to have different colors in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor status bar.</span></span> <span data-ttu-id="a49a7-133">Isso o ajuda a identificar a qual servidor cada janela de editor é conectada quando você tem muitas janelas abertas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="a49a7-133">This helps you identify which server each editor window is connected to when you have many windows open at the same time.</span></span> <span data-ttu-id="a49a7-134">Para obter mais informações sobre como definir cores da barra de status, veja [Barra de status &#40;Editor de Consultas do Mecanismo de Banco de Dados&#41;](status-bar-database-engine-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="a49a7-134">For more information about setting status bar colors, see [Status Bar &#40;Database Engine Query Editor&#41;](status-bar-database-engine-query-editor.md).</span></span>  
  
 <span data-ttu-id="a49a7-135">Alguns tipos de editores não exibem a barra de status ou não oferecem suporte a várias cores.</span><span class="sxs-lookup"><span data-stu-id="a49a7-135">Some types of editors do not display the status bar, or do not support multiple colors.</span></span>  
  
  
