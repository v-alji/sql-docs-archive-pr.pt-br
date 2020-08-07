---
title: Gerenciador de modelos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.wb.templates.f1
- sql12.swb.templates.explorer.f1
helpviewer_keywords:
- templates [SQL Server]
- SQL Server Management Studio [SQL Server], Template Explorer
- Template Explorer
- templates [Transact-SQL]
- templates [SQL Server], Template Explorer
ms.assetid: b9ee55c5-bb44-4f76-90ac-792d8d83b4c8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35e7ee1e6261c759580df3a836f9cc4b500a77ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575513"
---
# <a name="template-explorer"></a><span data-ttu-id="c34e1-102">Explorador de Modelos</span><span class="sxs-lookup"><span data-stu-id="c34e1-102">Template Explorer</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c34e1-103">fornece uma variedade de modelos.</span><span class="sxs-lookup"><span data-stu-id="c34e1-103">provides a variety of templates.</span></span> <span data-ttu-id="c34e1-104">Modelos são arquivos boilerplate que contêm scripts SQL que ajudam você a criar objetos em um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c34e1-104">Templates are boilerplate files containing SQL scripts that help you create objects in a database.</span></span> <span data-ttu-id="c34e1-105">Na primeira vez que o Gerenciador de modelos é aberto, uma cópia dos modelos é colocada na pasta do usuário em C:\Users, em AppData\Roaming\Microsoft\SQL Server Management Studio\120\Templates.</span><span class="sxs-lookup"><span data-stu-id="c34e1-105">The first time the template explorer is opened, a copy of the templates are placed in the user's folder in C:\Users, under AppData\Roaming\Microsoft\SQL Server Management Studio\120\Templates.</span></span>  
  
 <span data-ttu-id="c34e1-106">Você pode procurar os modelos disponíveis no Gerenciador de Modelos e, depois, abrir um modelo para incorporar o código em uma janela de editor de códigos.</span><span class="sxs-lookup"><span data-stu-id="c34e1-106">You can browse the available templates in Template Explorer, then open a template to incorporate the code into a code editor window.</span></span> <span data-ttu-id="c34e1-107">Você também pode criar modelos personalizados.</span><span class="sxs-lookup"><span data-stu-id="c34e1-107">You can also create custom templates.</span></span>  
  
## <a name="benefits-of-templates"></a><span data-ttu-id="c34e1-108">Benefícios de modelos</span><span class="sxs-lookup"><span data-stu-id="c34e1-108">Benefits of Templates</span></span>  
 <span data-ttu-id="c34e1-109">Os modelos estão disponíveis para soluções, projetos e vários tipos de editores de códigos.</span><span class="sxs-lookup"><span data-stu-id="c34e1-109">Templates are available for solutions, projects, and various types of code editors.</span></span> <span data-ttu-id="c34e1-110">Esses modelos estão disponíveis para criar objetos como bancos de dados, tabelas, exibições, índices, procedimentos armazenados, gatilhos, estatísticas e funções.</span><span class="sxs-lookup"><span data-stu-id="c34e1-110">Templates are available to create objects like databases, tables, views, indexes, stored procedures, triggers, statistics, and functions.</span></span> <span data-ttu-id="c34e1-111">Além disso, há modelos que o ajudam a administrar seu servidor criando propriedades estendidas, servidores vinculados, logons, funções, usuários e modelos para o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c34e1-111">In addition, there are templates that help you to manage your server by creating extended properties, linked servers, logins, roles, users, and templates for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c34e1-112">Os scripts de modelo fornecidos com o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] contêm parâmetros para ajudá-lo a personalizar o código.</span><span class="sxs-lookup"><span data-stu-id="c34e1-112">The template scripts provided with [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] contain parameters to help you customize the code.</span></span> <span data-ttu-id="c34e1-113">Quando você abrir um modelo, use a caixa de diálogo **Substituir Parâmetros do Modelo** para inserir valores no script.</span><span class="sxs-lookup"><span data-stu-id="c34e1-113">When you open a template, Use the **Replace Template Parameters** dialog box to insert values into the script.</span></span>  
  
 <span data-ttu-id="c34e1-114">Crie modelos personalizados para tarefas executadas com frequência.</span><span class="sxs-lookup"><span data-stu-id="c34e1-114">Create custom templates for tasks you perform frequently.</span></span> <span data-ttu-id="c34e1-115">Organize seus scripts personalizados nas pastas existentes ou crie uma nova estrutura de pastas.</span><span class="sxs-lookup"><span data-stu-id="c34e1-115">Organize your custom scripts into the existing folders or create a new folder structure.</span></span>  
  
 <span data-ttu-id="c34e1-116">O editor de consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] também oferece suporte a snippets de códigos que podem ser inseridos em locais específicos em um script clicando com o botão direito do mouse nesse local.</span><span class="sxs-lookup"><span data-stu-id="c34e1-116">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query editor also supports code snippets, which can be inserted at specific locations in a script by right-clicking at that location.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="c34e1-117">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="c34e1-117">Related Tasks</span></span>  
 <span data-ttu-id="c34e1-118">Use os tópicos a seguir como introdução rápida a modelos</span><span class="sxs-lookup"><span data-stu-id="c34e1-118">Use the following topics to get started with templates</span></span>  
  
|<span data-ttu-id="c34e1-119">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c34e1-119">**Description**</span></span>|<span data-ttu-id="c34e1-120">**Tópico**</span><span class="sxs-lookup"><span data-stu-id="c34e1-120">**Topic**</span></span>|  
|---------------------|---------------|  
|<span data-ttu-id="c34e1-121">Descreve como incorporar o código de um modelo em uma janela de editor de códigos.</span><span class="sxs-lookup"><span data-stu-id="c34e1-121">Describes how to incorporate the code from a template into a code editor window.</span></span>|[<span data-ttu-id="c34e1-122">Abrir um modelo</span><span class="sxs-lookup"><span data-stu-id="c34e1-122">Open a Template</span></span>](open-a-template.md)|  
|<span data-ttu-id="c34e1-123">Descreve como substituir valores de parâmetros de modelo depois de abrir um modelo em um editor de códigos.</span><span class="sxs-lookup"><span data-stu-id="c34e1-123">Describes how to replace template parameter values after opening a template in a code editor.</span></span>|[<span data-ttu-id="c34e1-124">Substituir parâmetros do modelo</span><span class="sxs-lookup"><span data-stu-id="c34e1-124">Replace Template Parameters</span></span>](replace-template-parameters.md)|  
  
  
