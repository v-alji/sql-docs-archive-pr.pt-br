---
title: Componentes de SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, about SQL Server Native Client ODBC driver
- data access [SQL Server Native Client], components
- components [SQL Server Native Client]
- SQLNCLI, about SQL Server Native Client
ms.assetid: 65f932d5-daa1-4eff-b6df-ee633fcf2a7c
author: rothja
ms.author: jroth
ms.openlocfilehash: 32438b9fb5473d9251acd0aceddb46db373f3548
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575082"
---
# <a name="components-of-sql-server-native-client"></a><span data-ttu-id="138b5-102">Componentes do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="138b5-102">Components of SQL Server Native Client</span></span>
  <span data-ttu-id="138b5-103">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client contém os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="138b5-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client contains the following components:</span></span>  
  
|<span data-ttu-id="138b5-104">Componente</span><span class="sxs-lookup"><span data-stu-id="138b5-104">Component</span></span>|<span data-ttu-id="138b5-105">Descrição</span><span class="sxs-lookup"><span data-stu-id="138b5-105">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="138b5-106">sqlncli11.dll</span><span class="sxs-lookup"><span data-stu-id="138b5-106">sqlncli11.dll</span></span>|<span data-ttu-id="138b5-107">O arquivo de biblioteca de vínculo dinâmico (DLL) que contém toda a funcionalidade do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="138b5-107">The dynamic-link library (DLL) file that contains all of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client functionality.</span></span> <span data-ttu-id="138b5-108">Isso inclui o provedor OLE DB do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client e o driver ODBC do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="138b5-108">This includes the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider and the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>|  
|<span data-ttu-id="138b5-109">sqlnclir11.rll</span><span class="sxs-lookup"><span data-stu-id="138b5-109">sqlnclir11.rll</span></span>|<span data-ttu-id="138b5-110">O arquivo de recursos que acompanha a biblioteca do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="138b5-110">The accompanying resource file for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client library.</span></span>|  
|<span data-ttu-id="138b5-111">s10ch_sqlncli.chm</span><span class="sxs-lookup"><span data-stu-id="138b5-111">s10ch_sqlncli.chm</span></span>|<span data-ttu-id="138b5-112">O arquivo de Ajuda do Assistente de Fonte de Dados que documenta como criar uma fonte de dados do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usando o driver ODBC do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ou o provedor OLE DB do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="138b5-112">The Data Source Wizard help file that documents how to create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data source using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver or the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span>|  
|<span data-ttu-id="138b5-113">sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="138b5-113">sqlncli.h</span></span>|<span data-ttu-id="138b5-114">O arquivo do cabeçalho do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client que contém todas as novas definições necessárias para usar o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="138b5-114">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client header file that contains all of the new definitions needed in order to use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="138b5-115">Esse arquivo de cabeçalho substitui os arquivos de cabeçalho odbcss.h e sqloledb.h.</span><span class="sxs-lookup"><span data-stu-id="138b5-115">This header file replaces both the odbcss.h and the sqloledb.h header files.</span></span> <span data-ttu-id="138b5-116">**Observação:**  Não é possível referenciar sqlncli. h e odbcss. h no mesmo programa, mas você pode fazer referência a sqlncli. h e SQLOLEDB. h no mesmo programa, contanto que SQLOLEDB. h seja definido primeiro.</span><span class="sxs-lookup"><span data-stu-id="138b5-116">**Note:**  You cannot reference sqlncli.h and odbcss.h in the same program, but you can reference sqlncli.h and sqloledb.h in same program as long as sqloledb.h is defined first.</span></span>|  
|<span data-ttu-id="138b5-117">sqlncli11.lib</span><span class="sxs-lookup"><span data-stu-id="138b5-117">sqlncli11.lib</span></span>|<span data-ttu-id="138b5-118">O arquivo de biblioteca necessário para chamar diretamente as funções do utilitário **bcp** que fazem parte do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client.</span><span class="sxs-lookup"><span data-stu-id="138b5-118">The library file needed to directly call the **bcp** utility functions that are part of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="138b5-119">**Observação:**  Se você fizer referência ao arquivo sqlncli11. lib no código de programação, precisará certificar-se de que o arquivo de sqlncli11.dll está no caminho do sistema e no caminho do sistema dos usuários que fazem uso do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="138b5-119">**Note:**  If you do reference the sqlncli11.lib file in your programming code, you need to make sure that the sqlncli11.dll file is in your system path, and in the system path of the users that make use of your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="138b5-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="138b5-120">See Also</span></span>  
 [<span data-ttu-id="138b5-121">Criando aplicativos com o SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="138b5-121">Building Applications with SQL Server Native Client</span></span>](building-applications-with-sql-server-native-client.md)  
  
  
