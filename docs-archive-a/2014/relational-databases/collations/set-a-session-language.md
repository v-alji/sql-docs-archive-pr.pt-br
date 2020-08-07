---
title: Definir um idioma da sessão | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- errors [SQL Server], international considerations
- globalization [SQL Server], sessions
- time [SQL Server]
- sessions [SQL Server], languages
- international considerations [SQL Server], sessions
- dates [SQL Server], session languages
- global considerations [SQL Server], sessions
- client-side session language
- time [SQL Server], session languages
- messages [SQL Server], international considerations
- server-side session language
ms.assetid: de7f2c90-8f4f-4cfc-94cc-4933a7fd2bde
author: stevestein
ms.author: sstein
ms.openlocfilehash: da8d6adce66ac5b97e533b5afaefabda40e4b966
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583648"
---
# <a name="set-a-session-language"></a><span data-ttu-id="62ddc-102">Definir um idioma de sessão</span><span class="sxs-lookup"><span data-stu-id="62ddc-102">Set a Session Language</span></span>
  <span data-ttu-id="62ddc-103">O idioma da sessão pode ser usado para definir como os seguintes elementos são exibidos no servidor com base na preferência cultural e de idioma:</span><span class="sxs-lookup"><span data-stu-id="62ddc-103">The session language can be used to set how the following elements are displayed on the server, based on language and cultural preference:</span></span>  
  
-   <span data-ttu-id="62ddc-104">O idioma que será usado para erros e outras mensagens do sistema.</span><span class="sxs-lookup"><span data-stu-id="62ddc-104">The language that will be used for error and other system messages.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="62ddc-105">dá suporte a várias cópias de todas as cadeias de caracteres de erros e de mensagens do sistema em todos os idiomas nos quais o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está disponível.</span><span class="sxs-lookup"><span data-stu-id="62ddc-105">supports having multiple copies of all system error strings and messages in all the languages in which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is available.</span></span> <span data-ttu-id="62ddc-106">Essas mensagens podem ser exibidas na exibição de catálogo [sys.messages](/sql/relational-databases/system-catalog-views/messages-for-errors-catalog-views-sys-messages) .</span><span class="sxs-lookup"><span data-stu-id="62ddc-106">These messages can be viewed in the [sys.messages](/sql/relational-databases/system-catalog-views/messages-for-errors-catalog-views-sys-messages) catalog view.</span></span> <span data-ttu-id="62ddc-107">Quando uma versão localizada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]é instalada, essas mensagens do sistema são traduzidas para a versão do idioma instalado.</span><span class="sxs-lookup"><span data-stu-id="62ddc-107">When you install a localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], these system messages are translated for the language version that you install.</span></span> <span data-ttu-id="62ddc-108">Por padrão, você também obtém o conjunto dessas mensagens em inglês (EUA).</span><span class="sxs-lookup"><span data-stu-id="62ddc-108">By default, you also obtain the U.S. English set of these messages.</span></span> <span data-ttu-id="62ddc-109">Além disso, é possível adicionar mensagens definidas pelo usuário em um idioma específico usando [sp_addmessage](/sql/relational-databases/system-stored-procedures/sp-addmessage-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="62ddc-109">Additionally, you can add user-defined messages in a specific language by using [sp_addmessage](/sql/relational-databases/system-stored-procedures/sp-addmessage-transact-sql).</span></span>  
  
-   <span data-ttu-id="62ddc-110">O formato de dados de data e hora.</span><span class="sxs-lookup"><span data-stu-id="62ddc-110">The format of date and time data.</span></span>  
  
-   <span data-ttu-id="62ddc-111">Os nomes de dias e meses, inclusive abreviações.</span><span class="sxs-lookup"><span data-stu-id="62ddc-111">The names of days and months, including abbreviations.</span></span>  
  
-   <span data-ttu-id="62ddc-112">O primeiro dia da semana.</span><span class="sxs-lookup"><span data-stu-id="62ddc-112">The first day of the week.</span></span>  
  
-   <span data-ttu-id="62ddc-113">Dados de moeda.</span><span class="sxs-lookup"><span data-stu-id="62ddc-113">Currency data.</span></span>  
  
 <span data-ttu-id="62ddc-114">Há 33 idiomas disponíveis para uso como configurações de sessão.</span><span class="sxs-lookup"><span data-stu-id="62ddc-114">There are 33 languages available for use as session settings.</span></span> <span data-ttu-id="62ddc-115">Para obter uma lista de idiomas, consulte [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="62ddc-115">For a list of languages, see [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql).</span></span>  
  
## <a name="setting-the-session-language-from-the-server"></a><span data-ttu-id="62ddc-116">Definindo o idioma da sessão no servidor</span><span class="sxs-lookup"><span data-stu-id="62ddc-116">Setting the Session Language from the Server</span></span>  
 <span data-ttu-id="62ddc-117">Para definir o idioma da sessão do lado de servidor, use [SET LANGUAGE](/sql/t-sql/statements/set-language-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="62ddc-117">To set the session language from the server side, use [SET LANGUAGE](/sql/t-sql/statements/set-language-transact-sql).</span></span>  
  
## <a name="setting-the-session-language-from-the-client"></a><span data-ttu-id="62ddc-118">Definindo o idioma da sessão no cliente</span><span class="sxs-lookup"><span data-stu-id="62ddc-118">Setting the Session Language from the Client</span></span>  
 <span data-ttu-id="62ddc-119">O idioma da sessão pode ser definido no lado do cliente usando o OLE DB, ODBC ou ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="62ddc-119">The session language can be set on the client side by using OLE DB, ODBC or ADO.NET.</span></span> <span data-ttu-id="62ddc-120">Para OLE DB, use a propriedade SSPROP_INIT_CURRENTLANGUAGE.</span><span class="sxs-lookup"><span data-stu-id="62ddc-120">For OLE DB, use the SSPROP_INIT_CURRENTLANGUAGE property.</span></span> <span data-ttu-id="62ddc-121">Para obter mais informações, consulte [Propriedades de inicialização e autorização](../native-client-ole-db-data-source-objects/initialization-and-authorization-properties.md).</span><span class="sxs-lookup"><span data-stu-id="62ddc-121">For more information, see [Initialization and Authorization Properties](../native-client-ole-db-data-source-objects/initialization-and-authorization-properties.md).</span></span>  
  
 <span data-ttu-id="62ddc-122">Para ODBC, use a palavra-chave Idioma.</span><span class="sxs-lookup"><span data-stu-id="62ddc-122">For ODBC, use the Language keyword.</span></span> <span data-ttu-id="62ddc-123">Para obter mais informações, consulte [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span><span class="sxs-lookup"><span data-stu-id="62ddc-123">For more information, see [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span></span>  
  
 <span data-ttu-id="62ddc-124">Para ADO.NET, use o parâmetro **Idioma Atual** do objeto **ConnectionString** .</span><span class="sxs-lookup"><span data-stu-id="62ddc-124">For ADO.NET, use the **Current Language** parameter of the **ConnectionString** object.</span></span> <span data-ttu-id="62ddc-125">Para obter mais informações, consulte a documentação do SDK do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Data Access Components (MDAC).</span><span class="sxs-lookup"><span data-stu-id="62ddc-125">For more information, see the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Data Access Components (MDAC) software development kit (SDK) documentation.</span></span>  
  
  
