---
title: Regras para inserção de valores de pesquisa (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- time [SQL Server], searches
- date searches
- dates [SQL Server], searches
- embedding apostrophes [SQL Server]
- logical value searches [SQL Server]
- case-sensitive search matches
- search criteria [SQL Server], rules
- text value searches [SQL Server]
- numeric value searches [SQL Server]
ms.assetid: 3c8134b7-83f4-41b4-99c8-e3949a685ff5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 907bcac93863bc5660993e910b37e25e25a129b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569802"
---
# <a name="rules-for-entering-search-values-visual-database-tools"></a><span data-ttu-id="ebe43-102">Regras para inserção de valores de pesquisa (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="ebe43-102">Rules for Entering Search Values (Visual Database Tools)</span></span>
  <span data-ttu-id="ebe43-103">Este tópico discute as convenções que devem ser usadas para inserir os seguintes tipos de valores literais em um critério de pesquisa:</span><span class="sxs-lookup"><span data-stu-id="ebe43-103">This topic discusses the conventions you must use when entering the following types of literal values for a search condition:</span></span>  
  
-   <span data-ttu-id="ebe43-104">Valores de texto</span><span class="sxs-lookup"><span data-stu-id="ebe43-104">Text values</span></span>  
  
-   <span data-ttu-id="ebe43-105">Valores numéricos</span><span class="sxs-lookup"><span data-stu-id="ebe43-105">Numeric values</span></span>  
  
-   <span data-ttu-id="ebe43-106">Datas</span><span class="sxs-lookup"><span data-stu-id="ebe43-106">Dates</span></span>  
  
-   <span data-ttu-id="ebe43-107">Valores lógicos</span><span class="sxs-lookup"><span data-stu-id="ebe43-107">Logical values</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ebe43-108">As informações contidas neste tópico derivam de regras para o SQL-92 padrão.</span><span class="sxs-lookup"><span data-stu-id="ebe43-108">The information in this topic is derived from the rules for standard SQL-92.</span></span> <span data-ttu-id="ebe43-109">No entanto, cada banco de dados pode implementar o SQL à sua própria maneira.</span><span class="sxs-lookup"><span data-stu-id="ebe43-109">However, each database can implement SQL in its own way.</span></span> <span data-ttu-id="ebe43-110">Assim, as diretrizes aqui fornecidas talvez não se apliquem a todos os casos.</span><span class="sxs-lookup"><span data-stu-id="ebe43-110">Therefore, the guidelines provided here might not apply in every case.</span></span> <span data-ttu-id="ebe43-111">Se você tiver dúvidas sobre como inserir valores de pesquisa em um banco de dados específico, recorra à documentação do banco de dados em uso.</span><span class="sxs-lookup"><span data-stu-id="ebe43-111">If you have questions about how to enter search values for a particular database, refer to the documentation for the database that you are using.</span></span>  
  
## <a name="searching-on-text-values"></a><span data-ttu-id="ebe43-112">Pesquisando valores de texto</span><span class="sxs-lookup"><span data-stu-id="ebe43-112">Searching on Text Values</span></span>  
 <span data-ttu-id="ebe43-113">As diretrizes a seguir são aplicadas quando se inserem valores de texto em critérios de pesquisa:</span><span class="sxs-lookup"><span data-stu-id="ebe43-113">The following guidelines apply when you enter text values in search conditions:</span></span>  
  
-   <span data-ttu-id="ebe43-114">**Aspas** Coloque valores de texto entre aspas simples, assim como neste exemplo de sobrenome:</span><span class="sxs-lookup"><span data-stu-id="ebe43-114">**Quotation marks** Enclose text values in single quotation marks, as in this example for a last name:</span></span>  
  
    ```  
    'Smith'  
    ```  
  
     <span data-ttu-id="ebe43-115">Ao inserir um critério de pesquisa no [Painel Critérios](visual-database-tools.md), basta digitar o valor de texto e o Designer de Consultas e Exibição colocará automaticamente o valor entre aspas simples.</span><span class="sxs-lookup"><span data-stu-id="ebe43-115">If you are entering a search condition in the [Criteria Pane](visual-database-tools.md), you can simply type the text value and the Query and View Designer will automatically put single quotation marks around it.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ebe43-116">Em alguns bancos de dados, os termos entre aspas simples são interpretados como valores literais, enquanto os termos entre aspas duplas são interpretados como objetos de banco de dados, por exemplo, referências de coluna ou tabela.</span><span class="sxs-lookup"><span data-stu-id="ebe43-116">In some databases, terms in single quotation marks are interpreted as literal values, whereas terms in double quotation marks are interpreted as database objects such as column or table references.</span></span> <span data-ttu-id="ebe43-117">Portanto, embora o Designer de Consulta e Exibição possa aceitar os termos com aspas duplas, ele poderá interpretá-los diferentemente do esperado.</span><span class="sxs-lookup"><span data-stu-id="ebe43-117">Therefore, even though the Query and View Designer can accept terms in double quotation marks, it might interpret them differently than you expect.</span></span>  
  
-   <span data-ttu-id="ebe43-118">**Incorporação de Apóstrofos** Se os dados sendo pesquisados contiverem uma aspa única (apóstrofo), insira duas aspas simples para indicar que você entende a aspa única como valor literal e não como delimitador.</span><span class="sxs-lookup"><span data-stu-id="ebe43-118">**Embedding apostrophes** If the data you are searching for contains a single quotation mark (an apostrophe), you can enter two single quotation marks to indicate that you mean the single quotation mark as a literal value and not a delimiter.</span></span> <span data-ttu-id="ebe43-119">Por exemplo, a condição a seguir pesquisa o valor "Caminho de Swann":</span><span class="sxs-lookup"><span data-stu-id="ebe43-119">For example, the following condition searches for the value "Swann's Way:"</span></span>  
  
    ```  
    ='Swann''s Way'  
    ```  
  
-   <span data-ttu-id="ebe43-120">**Limites de comprimento** Não exceda o comprimento máximo da instrução SQL do banco de dados quando inserir longas cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ebe43-120">**Length limits** Do not exceed the maximum length of the SQL statement for your database when entering long strings.</span></span>  
  
-   <span data-ttu-id="ebe43-121">**Diferenciação de maiúsculas e minúsculas** Siga as regras de diferenciação de maiúsculas e minúsculas do banco de dados em uso.</span><span class="sxs-lookup"><span data-stu-id="ebe43-121">**Case sensitivity** Follow the case sensitivity rules for the database you are using.</span></span> <span data-ttu-id="ebe43-122">O banco de dados em uso determina se as pesquisas de texto diferenciam maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ebe43-122">The database you are using determines whether text searches are case sensitive.</span></span> <span data-ttu-id="ebe43-123">Por exemplo, alguns bancos de dados interpretam o operador "=" como significando uma correspondência exata entre maiúsculas e minúsculas, mas outros permitem correspondências de qualquer combinação de caracteres maiúsculos e minúsculos.</span><span class="sxs-lookup"><span data-stu-id="ebe43-123">For example, some databases interpret the operator "=" to mean an exact case-sensitive match, but others will allow matches on any combination of uppercase and lowercase characters.</span></span>  
  
     <span data-ttu-id="ebe43-124">Se você não tiver certeza se o banco de dados utiliza pesquisa com diferenciação de maiúsculas e minúsculas ou não, use as funções UPPER ou LOWER no critério de pesquisa para converter as maiúsculas e minúsculas dos dados de pesquisa, como ilustrado no exemplo abaixo:</span><span class="sxs-lookup"><span data-stu-id="ebe43-124">If you are unsure about whether the database uses a case-sensitive search, you can use the UPPER or LOWER functions in the search condition to convert the case of the search data, as illustrated in the following example:</span></span>  
  
    ```  
    WHERE UPPER(lname) = 'SMITH'  
    ```  
  
## <a name="searching-on-numeric-values"></a><span data-ttu-id="ebe43-125">Pesquisando valores numéricos</span><span class="sxs-lookup"><span data-stu-id="ebe43-125">Searching on Numeric Values</span></span>  
 <span data-ttu-id="ebe43-126">As diretrizes a seguir são aplicada quando se inserem valores numéricos em critérios de pesquisa:</span><span class="sxs-lookup"><span data-stu-id="ebe43-126">The following guidelines apply when you enter numeric values in search conditions:</span></span>  
  
-   <span data-ttu-id="ebe43-127">**Aspas** Não inclua números entre aspas.</span><span class="sxs-lookup"><span data-stu-id="ebe43-127">**Quotation marks** Do not enclose numbers in quotation marks.</span></span>  
  
-   <span data-ttu-id="ebe43-128">**Caracteres não numéricos** Não inclua caracteres não numéricos, exceto o separador decimal (conforme definido na caixa de diálogo **Configurações Regionais** do Painel de Controle do Windows) e o sinal negativo (-).</span><span class="sxs-lookup"><span data-stu-id="ebe43-128">**Non-numeric characters** Do not include non-numeric characters except the decimal separator (as defined in the **Regional Settings** dialog box of Windows Control Panel) and negative sign (-).</span></span> <span data-ttu-id="ebe43-129">Não inclua símbolos que agrupam dígitos (como uma vírgula entre os milhares) ou símbolos de moeda.</span><span class="sxs-lookup"><span data-stu-id="ebe43-129">Do not include digit grouping symbols (such as a comma between thousands) or currency symbols.</span></span>  
  
-   <span data-ttu-id="ebe43-130">**Marcas decimais** Se você estiver digitando números inteiros, poderá incluir uma marca decimal, caso o valor pesquisado seja número inteiro ou real.</span><span class="sxs-lookup"><span data-stu-id="ebe43-130">**Decimal marks** If you are entering whole numbers, you can include a decimal mark, whether the value you are searching for is an integer or a real number.</span></span>  
  
-   <span data-ttu-id="ebe43-131">**Notação científica** Você pode inserir números muito grandes ou muito pequenos que usam notação científica, como neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="ebe43-131">**Scientific notation** You can enter very large or very small numbers using scientific notation, as in this example:</span></span>  
  
    ```  
    > 1.23456e-9  
    ```  
  
## <a name="searching-on-dates"></a><span data-ttu-id="ebe43-132">Pesquisando datas</span><span class="sxs-lookup"><span data-stu-id="ebe43-132">Searching on Dates</span></span>  
 <span data-ttu-id="ebe43-133">O formato usado para inserir datas depende do banco de dados que você está usando e do painel do Designer de Consulta e Exibição em que está inserindo as datas.</span><span class="sxs-lookup"><span data-stu-id="ebe43-133">The format you use to enter dates depends on the database you are using and in what pane of the Query and View Designer you are entering the date.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ebe43-134">Se você não souber qual é o formato usado pela fonte de dados, digite uma data na coluna de filtro do Painel de critérios em qualquer formato que lhe seja familiar.</span><span class="sxs-lookup"><span data-stu-id="ebe43-134">If you don't know which format your data source uses, type a date into the filter column of the Criteria pane in any format familiar to you.</span></span> <span data-ttu-id="ebe43-135">O Designer converterá a maioria dessas inserções para o formato apropriado.</span><span class="sxs-lookup"><span data-stu-id="ebe43-135">The designer will convert most of such entries into the appropriate format.</span></span>  
  
 <span data-ttu-id="ebe43-136">O Designer de Consulta e Exibição trabalha com os seguintes formatos de data:</span><span class="sxs-lookup"><span data-stu-id="ebe43-136">The Query and View Designer can work with the following date formats:</span></span>  
  
-   <span data-ttu-id="ebe43-137">**Específico de localidade** Formato especificado para datas na caixa de diálogo **Propriedades de Configurações Regionais do Windows** .</span><span class="sxs-lookup"><span data-stu-id="ebe43-137">**Locale-specific** The format specified for dates in the **Windows Regional Settings Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="ebe43-138">**Específico de banco de dados** Qualquer formato entendido pelo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ebe43-138">**Database-specific** Any format understood by the database.</span></span>  
  
-   <span data-ttu-id="ebe43-139">**Padrão de data ANSI** Formato que usa chaves; o marcador 'd' para designar a data e uma cadeia de caracteres de data, como no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="ebe43-139">**ANSI standard date** A format that uses braces, the marker 'd' to designate the date, and a date string, as in the following example:</span></span>  
  
    ```  
    { d '1990-12-31' }  
    ```  
  
-   <span data-ttu-id="ebe43-140">**Data e hora padrão ANSI** Semelhante à data padrão ANSI, porém usando 'ts' em vez de 'd' e adicionando horas, minutos e segundos à data (utiliza o formato de dia de 24 horas), como neste exemplo de 31 de dezembro de 1990:</span><span class="sxs-lookup"><span data-stu-id="ebe43-140">**ANSI standard datetime** Similar to ANSI-standard date, but uses 'ts' instead of 'd' and adds hours, minutes, and seconds to the date (using a 24-hour clock), as in this example for December 31, 1990:</span></span>  
  
    ```  
    { ts '1990-12-31 00:00:00' }  
    ```  
  
     <span data-ttu-id="ebe43-141">Em geral, o formato de data padrão ANSI é usado em bancos de dados que representam datas usando um tipo de dados de data real.</span><span class="sxs-lookup"><span data-stu-id="ebe43-141">In general, the ANSI standard date format is used with databases that represent dates using a true date data type.</span></span> <span data-ttu-id="ebe43-142">Por outro lado, o formato de data e hora é usado em bancos de dados que dão suporte ao tipo de dados de data e hora.</span><span class="sxs-lookup"><span data-stu-id="ebe43-142">In contrast, the datetime format is used with databases that support a datetime data type.</span></span>  
  
 <span data-ttu-id="ebe43-143">A tabela a seguir resume o formato de data que pode ser usado em diferentes painéis do Designer de Consulta e Exibição.</span><span class="sxs-lookup"><span data-stu-id="ebe43-143">The following table summarizes the date format that you can use in different panes of the Query and View Designer.</span></span>  
  
|<span data-ttu-id="ebe43-144">**Painel**</span><span class="sxs-lookup"><span data-stu-id="ebe43-144">**Pane**</span></span>|<span data-ttu-id="ebe43-145">**Formato de data**</span><span class="sxs-lookup"><span data-stu-id="ebe43-145">**Date format**</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="ebe43-146">Critérios</span><span class="sxs-lookup"><span data-stu-id="ebe43-146">Criteria</span></span>|<span data-ttu-id="ebe43-147">Padrão ANSI específico de Banco de dados e específico de localidade</span><span class="sxs-lookup"><span data-stu-id="ebe43-147">Locale-specific Database-specific ANSI standard</span></span><br /><br /> <span data-ttu-id="ebe43-148">As datas inseridas no [Painel Critérios](visual-database-tools.md) são convertidas em formato compatível com banco de dados no painel SQL.</span><span class="sxs-lookup"><span data-stu-id="ebe43-148">Dates entered in the [Criteria Pane](visual-database-tools.md) are converted to a database-compatible format in the SQL pane.</span></span>|  
|<span data-ttu-id="ebe43-149">SQL</span><span class="sxs-lookup"><span data-stu-id="ebe43-149">SQL</span></span>|<span data-ttu-id="ebe43-150">Padrão ANSI específico de banco de dados</span><span class="sxs-lookup"><span data-stu-id="ebe43-150">Database-specific ANSI standard</span></span>|  
|<span data-ttu-id="ebe43-151">Resultados</span><span class="sxs-lookup"><span data-stu-id="ebe43-151">Results</span></span>|<span data-ttu-id="ebe43-152">Específico de localidade</span><span class="sxs-lookup"><span data-stu-id="ebe43-152">Locale-specific</span></span>|  
  
## <a name="searching-on-logical-values"></a><span data-ttu-id="ebe43-153">Pesquisando valores lógicos</span><span class="sxs-lookup"><span data-stu-id="ebe43-153">Searching on Logical Values</span></span>  
 <span data-ttu-id="ebe43-154">O formato de dados lógicos varia entre os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="ebe43-154">The format of logical data varies from database to database.</span></span> <span data-ttu-id="ebe43-155">Muito frequentemente, um valor False é armazenado como zero (0).</span><span class="sxs-lookup"><span data-stu-id="ebe43-155">Very frequently, a value of False is stored as zero (0).</span></span> <span data-ttu-id="ebe43-156">Um valor True é armazenado com mais frequência como 1 e ocasionalmente como -1.</span><span class="sxs-lookup"><span data-stu-id="ebe43-156">A value of True is most frequently stored as 1 and occasionally as -1.</span></span> <span data-ttu-id="ebe43-157">As diretrizes a seguir são aplicadas quando se inserem valores lógicos em critérios de pesquisa:</span><span class="sxs-lookup"><span data-stu-id="ebe43-157">The following guidelines apply when you enter logical values in search conditions:</span></span>  
  
-   <span data-ttu-id="ebe43-158">Para pesquisar um valor False, use um zero, como no exemplo abaixo:</span><span class="sxs-lookup"><span data-stu-id="ebe43-158">To search for a value of False, use a zero, as in the following example:</span></span>  
  
    ```  
    SELECT * FROM authors  
    WHERE contract = 0  
    ```  
  
-   <span data-ttu-id="ebe43-159">Se você não tiver certeza do formato a ser usado durante a pesquisa de um valor True, tente usar 1, como no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="ebe43-159">If you are not sure what format to use when searching for a True value, try using 1, as in the following example:</span></span>  
  
    ```  
    SELECT * FROM authors  
    WHERE contract = 1  
    ```  
  
-   <span data-ttu-id="ebe43-160">Como alternativa, você pode ampliar o escopo da pesquisa procurando qualquer valor diferente de zero, como neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="ebe43-160">Alternatively, you can broaden the scope of the search by searching for any non-zero value, as in the following example:</span></span>  
  
    ```  
    SELECT * FROM authors  
    WHERE contract <> 0  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ebe43-161">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ebe43-161">See Also</span></span>  
 [<span data-ttu-id="ebe43-162">Especificar critérios de pesquisa &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="ebe43-162">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
