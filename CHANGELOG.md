# 2.3.0-alpha1

- #1823 Add states/provinces concept. The objective of this PR is to separate states/provinces of countries. For now, the concept of states/provinces was managed in country model which was not the best way.
- #1878 Add module code in the lists of the BackOffice for a better understanding.
- #1832 Language improvement. Add the possibility to disable a language. It's possible to disable the language only for the front.
- #1851 Add in the module Tinymce, the possibility to choose in which text areas the editor will be used.
- #1840 Add the possibility to generate an url with the arguments ```router``` and ```route_id``` in the smarty function ```url```. Documentation ```http://doc.thelia.net/en/documentation/templates/urls-and-paths.html```
- #1872 Add next/prev buttons for orders and customers. Modify the loops of brands, categories, folders and contents so that the queries to get the next and previous objects are sent only when it is needed.
- #1850 #1859 Add hooks for email template
- #1845 Add price including taxes in the combination creation pop-up in the BackOffice
- #1868 Allow to open order-edit.html template with a specific module tab
- #1861 Add links to the appropriate pages
- #1860 Change version of Symfony Yaml components
- #1843 Fix smarty form_collection_field, a performance problem was introduced after this PR: #1613 because ​the Form::createView() method create all form view on each call.
- #1856 Convert order.invoice_date to datetime column
- #1852 Add the possibility to disable the generation of url for the loops, adds argument ```return_url``` in loops, the default value for argument ```return_url``` is ```true```
- #1857 Fix of hookblack : order.tab
- #1792 Update module Carousel, change the location of saving of the images
- #1844 #1848 Added hooks in the right column part of the edtion form of brand, content, category folder and product templates :
    - ```brand.modification.form-right.top```, ```brand.modification.form-right.bottom```
    - ```category.modification.form-right.top```, ```category.modification.form-right.bottom```
    - ```content.modification.form-right.top```, ```content.modification.form-right.bottom```
    - ```folder.modification.form-right.top```, ```folder.modification.form-right.bottom```
    - ```product.modification.form-right.top```, ```product.modification.form-right.bottom```
- #1835 Add the product combination in PDF delivery
- #1788 Remove all the AdminIncludes from the core modules.
- #1841 Add the possibility to create a product combination with several same attribute inside (2 colors in one product sales elements).
- #1830 Fix attribute title in the modal "create a new combination"
- #1780 Currency improvements. Add the possibility to disable a currency. Add the possibility to change the position of the currency symbol. Resolve #1446
- #1825 Add message if thelia project is not installed
- #1714 #1839 #1833 Hook improvements
    - Add new syntax to hook on a hook. Documentation ```http://doc.thelia.net/en/documentation/modules/hooks/index.html```
    - Add command ```php Thelia hook```
- #1824 #1829 Fix the admin home stats, On page load, the month sent to Thelia was bad
- #1821 Fix the value for constant ```AdminForm::LANG_DEFAULT_BEHAVIOR```, Resolve ##1820
- #1818 Fix BackOffice menu, hook block to integrate main link if it's used
- #1816 Fix the total price of cart if the items have a quantity greater than one, Resolve #1772, add new methods ```getTotalRealTaxedPrice```, ```getTotalTaxedPrice```, ```getTotalTaxedPromoPrice``` in the model ```Thelia\Model\CartItem```
- #1783 Fix product price exports. Resolve #1078 #1610
- #1808 Add customer's company in order mails and PDF
- #1780 Adds the ability to disable a currency and change the position of the currency symbol
- #1806 Fix the event dispatched before decoding of the import, ```TheliaEvents::IMPORT_AFTER_DECODE``` to ```TheliaEvents::IMPORT_BEFORE_DECODE```
- #1799 Fixed the redirection to rewritten URL
- #1725 Added new attributes and some aliases to the {cart} substitution
    - A new `weight` attribute is added, to get the cart total weight.
    - A new `total_price_without_discount` attribute is added, to get the cart total amount without taxes, excluding discount.
    - The following aliases of existing attributes are added, to provide a better english syntax, or a more accurate name :
        - `product_count`, alias of `count_product`
        - `item_count`, alias of `count_item`
        - `total_price_with_discount` alias of `total_price`
        - `total_taxed_price_with_discount` alias of `total_taxed_price`
        - `contains_virtual_product` alias of `is_virtual`
        - `total_tax_amount` alias of `total_vat`
- #1802 After upload, The image file name is no longer the default image title
- #1805 Add a new parameter ```locale``` for the module_config smarty plugin
- #1796 Fix regression in OrderAddressEvent cell phone can not be required in the constructor
- #1787 Add loop Overriding, Documentation ```http://doc.thelia.net/en/documentation/loop/extend.html```
- #1785 Fix undesirable carts, persist only non empty carts
- #1790 Update the default PSE ref when the product ref is updated
- #1778 #1797 Add ```manual``` and ```manuel_reverse``` order in attributeCombination loop
- #1766 Add order by ```id``` and ```id_reverse``` in product_sale_element loop
- #1760 Set order status as paid when the FreeOrder module is used to "pay" an order
- #1751 Fix for undefined currency exchange rate, add error message in the currency configuration page when an exchange rate could not be found
- #1769 Increase API key size to 48
- #1771 Add argument ```customer_id``` for hook customer.edit-js
- #1753 Fix the rounding of prices in the order product loop
- #1768 Update composer.lock file, update of the dependency thelia/currency-converter to version 1.0.1
- #1752 Add addValues method in EnumListType
- #1746 Removes deprecated classes and methods for the version 2.3
- #1745 Fix output value IS_DEFAULT in the product_sale_elements loop
- #1754 Add homepage redirection on /admin/login if the admin is already authenticate. Before this change, there was a render
- #1765 Fix for prev/next queries in Category and Content loops, and add prev/next in Product and Folder loop
- #1759 Fix for parent attribute and new exclude_parent attribute of Category loop
- #1750 Add EQUAL to product loop filter by min or max
- #1727 Add template & stock inputs on product creation
- #1722 Replaced parameter "locale" with "lang" in generated URL
- #1732 Update sql constraint for table product_sale_elements_product_image and product_sale_elements_product_document
- #1730 Change layout to only cache assets/dist
- #1734 Fix critical performance issue on ProductController HydrateObjectForm
- #1733 Fix order attribute in BaseHook
- #1729 Fix all useless DIRECTORY_SEPARATOR
- #1726 Fix method setRangeDate variable
- #1718 Autocomplete combination generation form with default pse values
- #1699 Fix missing use for BirthdayType
- #1713 Add more options for content, folder and order in search results
- #1706 Fix form coupon not found in frontOffice order invoice
- #1700 Fix source priority in ```ParserContext::getForm```
- #1588 Add document tab in frontOffice product page
- #1668 Add height limit for the select fields in the Attributes and Features tab of the admin product edit page
- #1669 Add options ```exclude_status, status_code, exclude_status_code``` and output value ```STATUS_CODE``` in Order loop
- #1674 Add options ```free_text, exclude_free_text``` in FeatureValue loop
- #1725 Add `weight` and `total_price_without_discount` attributes to the `{cart}` substitution, and some aliases to provide a better english syntax, or a more accurate name to existing attributes : `product_count`, alias of `count_product`, `item_count`, alias of `count_item`, `total_price_with_discount` alias of `total_price`, `total_taxed_price_with_discount` alias of `total_taxed_price`, `contains_virtual_product` alias of `is_virtual`, `total_tax_amount` alias of `total_vat`

# 2.2.0

- #1692 Fix amounts displayed on the PDF invoice when a postage with tax is used (fixes #1693 and #1694)
- #1692 Fix translations for HookNavigation module
- #1692 Update hooktest-template and hooktest-module to prevent thelia-installer conflicts
- #1692 Update French, German, Italian translations
- #1692 Add Turkish translation
- #1688 Fix the permission messages in Thelia installer
- #1686 Use createForm method for front forms ```thelia.coupon.code, thelia.order.delivery, thelia.order.payment```
- #1667 Fix #1666 Display an error when trying to delete a customer which has orders
- #1665 Fix form field type date in Smarty plugin form, checks if the field type is a BirthdayType for assign a smarty variable [years, month, days]
- #1659 Fix Administrator edit action in the BackOffice, it was impossible to edit an administrator

# 2.2.0-beta3

- #1653 Remove ```AdminIncludes``` folder in the module generation
- #1649 Add index in table rewriting_url
- #1644 Allow relative path use with Tlog
- #1640 Add docker and docker-compose configuration
- #1637 Fix admin API edit button
- #1635 Add unit tests for the routing files (admin, api, front)
- #1634 Remove leftover uncallable routes (admin)
- #1631 Remove duplicate route (admin)
- #1629 Fix errors reporting of admin hooks
- #1632 Fix pagination infinite URL ; redirect on page 1 when changing products per page limit to avoid having no product on the page
- #1616 Improve statistic on homepage, add datetimepicker and fix first order
- #1601 Add set error in TheliaFormValidator when form is not valid
- #1585 Add parameters in frontOffice hooks
- #1587 Fix redirect url for the folder image and folder document
- #1590 Fix Thelia request initialization
- #1593 Fix form serialization in session that contain uploaded files
- #1594 update symfony/validator version to 2.3.31
- #1598 composer.json update dependency fzaninotto/faker to stable version 1.5
- #1583 Add German translations
- #1615 New TheliaEvents::CART_FINDITEM event to improve cart management flexibility
- #1618 Configurable faker
- #1581 Fix the prices precision
    - Not round the prices without tax in back office
    - Change the type for the price columns in database. New type : decimal(16,6)

##DEPRECATED

- Deprecated AdminIncludes, it's better to use the hooks

# 2.2.0-beta2

- Add module image edition in backoffice
- The language change links should now use the locale instead of the language code, e.g. http://www.yourshop/some-page?lang=fr_FR instead if http://www.yourshop/some-page?lang=fr. Backward compatibility is provided.
- Order status added by modules have their CSS label color handled or have a default color
- New login page style
- New general style of backoffice
- New dashboard arrangement

# 2.2.0-beta1

- Fix currency create action to set the by_default field properly.
- Add missing column default_template_id in category_version table
- The product parameter of the feature_value loop is no longer mandatory
- The product parameter new $PRODUCT variable is deprecated. $PRODUCT_ID should be used instead.
- Fix smarty `format_date` function to use consistent format when `locale` attribute is used.
- A product and all it's dependencies can now be cloned
- Fix index form error information session cleaning
- Feature's free text values now handle i18n
- URLs now have no problem with accents or case
- Add order by ```weight``` and ```weight_reverse``` in  product sale elements loop
- Add the ability to remove arguments in loops.
- new back-office is enhanced with a group button actions and a new layout
- Added an optional 'ajax-view' parameter to card add form
- Add validation groups in form from parser context
- Feature value are not translatable
- Allow multiple authors in module.xml file. Fixed #1459
- Display the mini cart with a hook. Fixed #1233
- Add date range for order export
- Klik&Pay is no more a submodule

# 2.2.0-alpha2

- Add a front office way to make an address the default one
- New translation domain that allows to redefine translation strings globally or specifically to a domain. By the way, we can safely update Thelia, modules, templates without overwriting specific translations.
- Remove ```currency_rate_update_url``` in ```setup/insert.sql```
- Add Cellphone to order address
- Add AnyListTypeArgument for loop argument
- New command ```module:position```. This command can changes module position
- Fix session serialisation
- Create a template context
- Allow relative path for the file logger from THELIA_ROOT constant
- Form error information are stored in the user session
- Fix redirection with slash ended uri. Fix #1331
- Config ```images_library_path``` and ```documents_library_path``` are now used everywhere
- Messages dispatched before and after content creation
- Add link to open pdf directly in browser in BO order/update
- Added wysiwyg.js hook where it was missing.
- Fix hook attribute in pdf template. The hook was never called.
- Cellphone column Added in order_address table
- Default front office template revamped :
    - bower and grunt can be used (but not mandatory, you can still use assetic)
    - less than 4095 css selectors (IE9 compatibility)
    - bootstrap is now fully used
    - this template is documented in its readme
- Force locale in session when loading a rewriten url
- Thelia is now fully usable with HTTPS protocol
- Do not delete the default product_sale_elements when the template of a product change
- Added standard 'error_url' parameter, like 'success_url'
- controller type can be found in the request (#1238)
- new helper to get order weight
- update selected delivery address in order process when customer change it
- new hooks for delivery modules in backoffice and pdf to add extra information

# 2.2.0-alpha1

- Add module code ($CODE variable) into payment loop outputs
- Add the 'images-folder' tag into module.xml file to deploy the modules images
- Add the 'module:list' command, that shows the modules state
- Update Admin Logs to add the resource ID when available.
- Add render smarty function, that executes the controller given in the action parameter.
- Allow modules to use document and image loop with the ```query_namespace``` argument
- Enable image zoom in image loop before cropping to guarantee that the resulting image will match the required size, even if the original image is smaller. This feature is active only if the ```allow_zoom``` parameter is true.
- When in development mode, an exception is thrown when an error occurs when processing assets, thus helping to diagnose missing files, LESS syntax errors, and the like.
- Change default order for cart loop
- New module_config Smarty function: {module_config module="module-code" key="parameter-name}
- Do not register previous url on XmlHttpRequest
- Add ACL on documents and images tabs.
- Add confirmation modal on documents deletion
- Add shop language choice on install wizard
- Remove redundant * on product-edit
- Add parameter "page_param_name" for template admin pagination.html. if "page_param_name" is empty, then the name of the parameter is "page"
- Add "Refunded" order status
- Add environment specific config file loading in modules
- Add the possibility for customers to change their email, backoffice configuration variables customer_change_email
- Add confirmation email for customers, backoffice configuration variables customer_confirm_email
- Refactor ```Thelia\Controller\BaseController::createForm``` into a factory service ```Thelia\Core\Form\TheliaFormFactory```
- Refactor ```Thelia\Controller\BaseController::validateForm``` and ```Thelia\Controller\BaseController::getErrorMessages``` into a service ```Thelia\Core\Form\TheliaFormValidator```
- Add the `failsafe=[true|false]` parameter to the assets Smarty functions (stylesheets, images, javascripts).
- A country could belong to more than one shipping zone.
- Add the `exclude_area` parameter to the Country loop.
- The Country loop now returns a proper country ISO code, left-padded with zeros, e.g. '004' instead of '4'
- The Country::getAreaId() method is DEPRECATED.
- Add the `country` and `order` parameters to Area loop
- Add the `area` parameter to Module loop
- Improved Shipping zones management
- Add cache on the graph of the home page, possibility to disable cache or change ttl cache, with the configuration variable admin_cache_home_stats_ttl
- New feature: a default product template could be defined in categories. Products created in this category will get this default product template. If no default product template is defined in a given category, it will be searched in parent categories.
- New main navigation style and position
- jquery.ui.datepicker is now DEPRECATED and will be REMOVED in 2.3. Please use boostrap-datepicker
- Add ```thelia.logger``` service to prepare the transition with another logger.
- Add 62 new admin hook
- Add stacked current form into parser context. It allows to have nested forms while using the new way to write forms.
- Module information and documentation could be viewed directly from the module list
- Add the possibility to translate text in the sql files (insert.sql, update/sql/\*.sql). to generate sql files use command `php Thelia generate:sql`. Translation can be made in the back office, in the translation page.
- format_date smarty function now handle symfony form type ```date```, ```datetime``` and ```time``` view value.
- Allow BaseController::generateOrderPdf to generate a pdf without having the rights
- SHOW_HOOK now displays parameters
- Add fallback for email template for mails sent from a module. If the template file does not exist in the current email template, it will use the one that comes with the module.
- Add dispatch of console events
- Refactor VirtualProductDelivery module. The email sending is now triggered from a new event to gain more flexibility. Now, email messages use smarty file templates located in `templates/email/default`.
- Added capability to use translator in module functions `preActivation` and `postActivation`
- Add environment aware database connection
- new 'asset' Smarty function, to get the URL of an arbitrary file from template assets, such as a video or a font.
- Imagine package is updated to 0.6.2, which provides a better support for transparency.
- Default border color of images resized with resize_mode="border" is now transparent instead of opaque white.
- The TemplateHelper class is deprecated. You should now use the thelia.template_helper service. TemplateHelperInterface has been introduced, so that modules may implement alternate versions


# 2.1.6

- Fix amounts displayed on the PDF invoice when a postage with tax is used (fixes #1693 and #1694).
- Check virtualProducts of order before send mail ```mail_virtualproduct```
- Add 'step' to input type number to be able to create and edit weight slices price
- Fix pagination infinite URL ; redirect on page 1 when changing products per page limit to avoid having no product on the page
- Allow relative path use with Tlog
- Prevent obscure "[] this value cannot be null" messages.
- Prevent short research and keep research in input
- Fix meta return array
- Fix hook position
- Fix Protocol-relative URL for HTTPS
- Update Copyright
- Fix translations and standardize Import and Export texts
- Fix the prices precision

# 2.1.5

- Klik&Pay is no more a submodule
- default category's parent is now 0
- check specific role in security module instead of checking if a user is logged in
- add a customer page parameter for the order loop on the customer page 
- keep break line in ACE editor

# 2.1.4

- Add ```export.top``` and ```export.bottom``` hooks
- Fix slash ended rewritten url redirection
- Remove ```currency_rate_update_url``` in ```setup/insert.sql```
- Allow relative path for the file logger from THELIA_ROOT
- Fixed product loop behavior when category_default is set
- Force locale in session when loading a rewriten url
- Add port parameter for installing thelia with cli tools
- Change default param of the isPaid function, true is the good default parameter.

# 2.1.3

- Add ```\Thelia\Model\OrderProduct::setCartItemId``` and ```\Thelia\Model\OrderProduct::getCartItemId``` to remove the typo with ```cartIemId```
- A notice is displayed when the product's template is changed
- Security fix on authentication
- Rename cookie related config variables. They were prefixed with "thelia_" on insert, but not in the code

## DEPRECATED

- ```\Thelia\Model\OrderProduct::setCartIemId``` Because of a typo
- ```\Thelia\Model\OrderProduct::getCartIemId``` Because of a typo too

# 2.1.2

- Add the possibility to delete a coupon from the backoffice.
- module list is now reversed. Delivery modules appear first, then payment and finally classic modules.
- display a loader when a module is uploaded
- Change product prices export and import format to be compatible, now using product_sale_elements id as key to identify PSE.
- Fix unused variable in ```Thelia\Controller\Api\CustomerController::getDeleteEvent```
- change default order for cart loop.
- Add missing static keyword for ```Thelia\Core\HttpFoundation\JsonResponse::createError```
- Do not register previous url on XmlHttpRequest
- Fix deploy image directory destination
- Fix redirect response if a AuthenticationException is catched
- The PaymentModule log default level is now INFO instead of ERROR
- Direct instantiations of Thelia forms is deprecated. BaseController::createForm() should be used instead.
- Prevent XSS injection in error.html template
- The hook method is now stored in the ignored_module_hook table
- Allow to hardlink TinyMCE rather than symlink
- Add bootstrap paths for thelia-project
- Enlarge order dropdown menu to prevent wrapping in some languages
- Fixed langugage when previewing e-mails

# 2.1.1

- Fix update process from Thelia 2.0.* to 2.1.*

# 2.1.0

- abilities to translate email and pdf templates in modules
- support of taxes for postage amount
- sales modify price on update only if the sale is currently active
- cart can be used without thelia cart cookie. Set cart.use_persistent_cookie to 0 in your config variable panel.
- hook contains more information like the id of the current object you are working on.
- fix module skeleton location


# 2.1.0-beta2

- config :
    - environment variable can be used in the database.yml file. See [https://github.com/thelia/thelia/pull/968](https://github.com/thelia/thelia/pull/968)
    - Allow other projects to override thelia directories constants by using composer "autoload"["file"] entries
- smarty:
    - Add the "current" argument on smarty "url" function that allows you to get the same page but with differant url parameters
- new method ```manageStockOnCreation``` in PaymentModuleInterface. If return false, the stock will be decreased on paid status instead of order creation.
- Thelia:
    - Split Thelia on multiple repositories to allow a better version management with composer. For creating a new project, see [https://github.com/thelia/thelia-project]
    - Extract all the default modules into other repositories
    - Field type :
        - added area_id, category_id, folder_id, content_id
        - thelia type support render_form_field
- loop `product_sale_elements` : added `ref` argument and implemented `SearchLoopInterface`
- Updated `hasVirtualProduct`  in `Order` model to not test the presence of filename, as modules could implement the process differently
- new method ```Thelia\Model\Module::getDeliveryModuleInstance()``` return the delivery module instance for the current record.
- 'freesans' is now the default font of PDF documents
- Anonymous cart is no longer duplicated on customer login


# 2.1.0-beta1

- Autoload : the autoloader can be cached with Apc or XCache. See new index.php file.
- Update : add missing API table creation
- The default Tlog level is now TLog::ERROR instead of Tlog::DEBUG
- Add error message pages instead of white pages. But you can disable them by setting 0 into the config variable "error_message.show".
- Front Office Template: new page to display the details of an order
- email can be previewed in the back office
- some smarty classes are still present in the core of thelia not to break backward compatibility. Those classes will be deleted in version 2.3 :
    * Thelia\Core\Template\Smarty\AbstractSmartyPlugin
    * Thelia\Core\Template\Smarty\SmartyPluginDescriptor
- the default address label is now translated
- fixed "strictly use the requested language"
- new config variable :
    * session_config.lifetime : Life time of the session cookie in the customer browser, in seconds
    * error_message.show : Show error message instead of a white page on a server error
    * error_message.page_name : Filename of the error page. Default : error.html
- All cs issues are fixed, Thelia is now fully PSR2 compliant
- Allow possibility to upload a module with github suffix (eg : paypal-master.zip)
- Added a fallback for template to use the default template. it's useful for modules that are used on a website that doesn't use the default template

# 2.1.0-alpha2

- Update Process :
    - update command has been removed and replaced by a php script and a web wizard. Read the UPDATE.md file
- Templating :
    - Smarty is now a dedicated Module and no more present in the core of Thelia
    - All the template logic works now with abstracted class or interface, so it is possible to create a new Module for
an other template engine
    - A new interface has been introduced, the ParserHelperInterface : its purpose is to parse a string and get all
parser's function and block with theirs arguments.
    - A new service has been introduced : thelia.parser.helper and it must be the implementation of ParserHelperInterface
    - If you want to create a new Template module, you must declare those services :
        - thelia.parser : the class that implements ParserInterface
        - thelia.parser.helper : the class that implements ParserHelperInterface
        - thelia.parser.asset.resolver : the class that implements AssetResolverInterface
- Routing :
    - new notation ```a:b:c``` => ```Foo:Bar:Baz``` will execute ```Foo\Controller\BarController::BazAction``` method
- Module :
    - New schema for modules
    - Module installation from back office
    - Dependency check to Thelia version and other modules during installation, activation, deactivation and deletion
- Smarty :
    - new plugin ```flash``` to support symfony flash message.
    - new plugin ```default_locale```. This function is used for forcing the usage of a specific locale in all your template. Useful for email and pdf. eg : ```{default_locale locale="en_US"}```
    - function ```intl``` has a new argument : ```locale```. If used, this locale will be used instead of session's locale
- Loop :
    - new method addOutputFields in order to add custom fields in an overridden loop
- Tests:
    - Move tests from ```core/lib/Thelia/Tests``` to ```tests/phpunit/Thelia/Tests```
    - Update PHPUnit from 4.1.3 to 4.1.6
- Symfony components:
    - Update from 2.3.* to 2.3.21
- REST API:
    - Implement the first version of the REST API. You can find the documentation [here](http://doc.thelia.net/en/documentation/api/authentication.html)
- Forms: New implementation of Symfony form component that now handles form types, form extensions and form type extensions
    - You can use the tags ```thelia.form.type```, ```thelia.form.extension``` and ```thelia.form.type_extension``` to declare yours
    - Implementation of many form types for thelia, see the namespace Thelia\Core\Form\Type

## DEPRECATED

- ```\Thelia\Core\HttpFoundation\Session\Session::getCart``` is deprecated. Use ```getSessionCart``` instead.
- ```\Thelia\Cart\CartTrait``` trait is deprecated. Use ```\Thelia\Core\HttpFoundation\Session\Session::getSessionCart``` for retrieving a valid cart.

#2.1.0-alpha1

- Added sale management feature
- Added `module_id` parameter to Area loop
- Added "Shipping configuration" button to the delivery module list, with a warning if no shipping zone is assigned to the module.
- Added the `show_label` parameter to the `render_form_field Smarty` function.
- Added the `exclude` parameter to `form_hidden_field` function.
- Added the `product` parameter to the `attribute_availability` loop.
- Added the `sale` parameter to the `product` loop.
- Added visible argument to image/document classes
- Added `new`, `promo` and `default` parameters to `product_sale_elements` loop
- Added `store_notification_emails`, which contains the recipients of shop notification (such as order placed)
- Added admin notification e-mail for order placed
- Improved other emails (specially text versions)
- Added ORDER_SEND_NOTIFICATION_EMAIL event
- class-loader component is removed, it was not used anymore.
- Updating stock when changing order : canceled status
- Added virtual products feature.
    - Added new delivery module for virtual products.
- Added meta data feature to associate core elements and various data.
- Added `allow_negative_stock` configuration variable to allow negative stock or not (default is no)
- Added the ModuleConfig table, to provide modules an easy way to store their configuration parameters, with I18n if required.
- Added the `module-config` loop
- Added getConfigValue() and setConfigValue() static helper methods to BaseModule to offer an easy way to get/set a module parameters
- Refactored the Cheque module, to use the new ModuleConfig, and send an email to the customer when its payment is received.
- Added the wysywig.js hook to official hooks, so that any page which needs a WYSYWIG editor will only have to put this hook in the JS section to get one.
- Refactored Tynimce module according to wysywig.js hook
- Moved cart and order flush in the Order action, triggered by the ORDER_CART_CLEAR event. Payment modules which redirects to a non-strandard route (e.g., not /order/placed/{order_id}) should fire this event.
- Refactored assets generation.
- `file` parameter of asset related smarty functions (`stylesheets`, `javascripts`, ìmages`, ...) should not contains ../
- Added remember me feature for customer sign in process

##DEPRECATED

Redirect methods are deprecated. You have now two ways for generating a redirect response :
- Throwing a Thelia\Core\HttpKernel\Exception\RedirectException with a given URL
- If you are in a controller, return an instance of \Symfony\Component\HttpFoundation\RedirectResponse
- Never ever send a response. Only the HttpKernel class is allowed to do that.

### Deprecated methods :

- Thelia\Controller\BaseController::redirect
- Thelia\Controller\BaseController::redirectSuccess
- Thelia\Controller\BaseController::redirectToRoute


# 2.0.10

- Add 'step' to input type number to be able to create and edit weight slices price
- Fix pagination infinite URL ; redirect on page 1 when changing products per page limit to avoid having no product on the page
- Allow relative path use with Tlog
- Prevent obscur "[] this value cannot be null" messages.
- Prevent short research and keep research in input
- Fix Protocol-relative URL for HTTPS
- Fix fatal error that occurs when store does not use the default order_configuration email

# 2.0.9

- Klik&Pay is no more a submodule

# 2.0.8

- Allow relative path from thelia root for the file logger (by default log/log-thelia.txt)
- Force rediction on admin login even when connected to the front

# 2.0.7

- Change TokenProvider behavior to be more flexible
- More secure csrf token
- Fix ```templates/backOffice/default/includes/inner-form-toolbar.html``` change currency destination
- Fix install bug if the admin password doesn't match

# 2.0.6

- Do not register previous url on XmlHttpRequest

# 2.0.5

- add new function to smarty ```set_previous_url```. The parameter ```ignore_current``` allows you to ignore the current url and it will not be store as a previous url
- 'freesans' is now the default font of PDF documents
- fix bug with cart foreign key constraint #926
- fix typo with '}' #999
- add missing 'admin.search' resource
- add default translation for '/ajax/mini-cart'
- fix product add to cart
- fix form firewall variable name
- add more module includes in order-edit.html
- do not allow failure anymore on travis php5.6

#2.0.4

- Updating stock when changing order : canceled status
- order table is versionnable now.
- product_sale_elements_id is added to order_product table.

#2.0.3

- Fix js syntax in order-delivery template
- price are now save without any round.
 /!\ Check in your templates if you are using format_money or format_number function. Don't display prices directly.
- change Argument type for ref parameter in Product loop
- Fix export template
- [Tinymce]fix invisible thumb in file manager

#2.0.3-beta2

- fix update process
- fix coupons trait
- update schema adding new constraints on foreign keys
- previous url is now saved in session. use ```{navigate to="previous"}``` in your template

#2.0.3-beta

- New coupon type: Free product if selected products are in the cart.
- New feature: Product Brands / Suppliers management
- New 'brand' loop and substitution. product, image and document loop have been updated.
- Images and document processing have been refactored.
- Added store description field for SEO
- Added code editor on textarea on email templates page
- Fixed issues on position tests
- Fixed issues on RSS feed links
- Update SwiftMailer
- Fix bugs on customer change password form and module "order by title"
- Add the ability to place a firewall on forms. To use this in a module, extend Thelia\Form\FirewallForm instead of BaseForm
- Add Exports and Imports management
- Default front office template:
     - Display enhancement
     - Optimization of the uses of Thelia loops to gain performances and consistency
     - Optimization for SEO : meta description fallback, title on category page, ...
     - new PSE layout in product page, attributes are separated
     - Support of 'check-available-stock' config variable
     - Terms and conditions agreement is now in the order process
- Default pdf template:
     - Added list of amount by tax rule
     - Display enhancement
     - Added legal information about the store
- Demo:
     - Support for brand
     - Added folders and contents data.

#2.0.2

- Coupon UI has been redesigned.
- New coupon types:
    - Constant discount on selected products
    - Constant discount on products of selected categories
    - Percentage discount on selected products
    - Percentage discount on products of selected categories
- New coupon conditions :
    - Start date
    - Billing country
    - Shipping country
    - Cart contains product
    - Cart contains product from category
    - For specific customers
- Free shipping can now be restricted to some countries and/or shipping methods
- session initialization use now event dispatcher :
    - name event : thelia_kernel.session (see Thelia\Core\TheliakernelEvents::SESSION
    - class event : Thelia\Core\Event\SessionEvent
    - example : Thelia\Core\EventListener\SessionListener
- Creation of Thelia\Core\TheliakernelEvents class for referencing kernel event
- Add new command line that refresh modules list `Thelia module:refresh`
- Coupon internals have been simplified and improved.
- Error messages are displayed in install process
- Add pagination on catalog page in Back-Office
- Add Hong Kong to country list
- Fixed issue #452 when installing Thelia on database with special characters
- implement search on content, folder and category loop.
- all form are documented
- template exists for managing google sitemap : sitemap.html

#2.0.1

- possibility to apply a permanent discount on a customer
- display estimated shipping on cart page
- export newsletter subscribers list
- Fix redirect issues
- enhancement of coupon UI
- enhancement of admin menu. Coupon is now in Tools menu
- front office, email and pdf templates are translated in Russian and Czech
- fix bugs : https://github.com/thelia/thelia/issues?milestone=4&page=1&state=closed

#2.0.0

- Coupons values are re-evaluated when a product quantity is changed in the shopping cart
- You can declare new compilerPass in modules. See Thelia\Module\BaseModule::getCompilers phpDoc
- Add ability to load assets from another template. See https://gist.github.com/lunika/9365180
- allow possibility to use Dependency Injection compiler in Thelia modules
- Add Deactivate Module Command Line
- Add indexes to  database to improve performance
- Order and customer references are more human readable than before
- Refactor intl process. A domain is created for each templates and modules :
    - core => for thelia core translations
    - bo.template_name (eg : bo.default) => for each backoffice template
    - fo.template_name (eg : fo.default) => for each frontoffice template
    - pdf.template_name (eg : pdf.default) => for each pdf template
    - email.template_name (eg : email.default) => for each email template
    - modules :
        - module_code (eg : paypal) => fore module core translations
        - module_code.ai (eg : paypal.ai) => used in AdminIncludes templates
        - bo.module_code.template_name (eg : bo.paypal.default) => used in back office template
        - fo.module_code.template_name (eg : fo.paypal.default) => used in front office template
- new parameter for smarty ```intl``` function. The parameter ```d``` allow you to specify the translation domain (as explain before). This parameter is optional
- the ```d``` can be omitted if you use ```{default_translation_domain domain='bo.default'}``` in your layout. If you use this smarty function, the ```d``` parameter is automatically set with the domain specify in ```default_translation_domain``` function
- We changed Thelia's license. Thelia is published  under the LGPL 3.0+ License


#2.0.0-RC1

- Remove container from BaseAction.
- fix sending mail on order creation
- less files in default templates are already compiled in css.
- all validator message are translated
- type argument is now a default argument and used for generating loop cache
- fix total amount without discount in backoffice. Fix #235
- description is not required anymore in coupon form. Fix #233
- Do not allow to cumulate the same coupon many times. Fix #217
- colissimo module is now fully configurable
- test suite are executed on PHP 5.4, 5.5, 5.6 and HHVM. Thelia is not fully compatible with HHVM
- add new attributes to loop pager (http://doc.thelia.net/en/documentation/loop/index.html#page-loop)
- we created a new github repo dedicated for modules : https://github.com/thelia-modules

#2.0.0-beta4

- Tinymce is now a dedicated module. You need to activate it.
- Fix PDF creation. Bug #180
- Fix many translation issues.
- The TaxManager is now a service
- Loop output is now put in cache for better performance
- loop count is refactored. It used now count propel method instead of classic loop method
- UTF-8 is used during install process, no more encoding problem in database now
- an admin can now choose a prefered locale and switch language in admin panel
- module repository is available on github : https://github.com/thelia-modules
- import module from Thelia 1 is available. It works from Thelia 1.4.2 : https://github.com/thelia-modules/importT1

#2.0.0-beta3

- Coupon effect inputs are now more customisable (input text, select, ajax, etc.. are usable) and unlimited amount of input for coupon effect are now possible too
- when a category is deleted, all subcategories are deleted
- delete products when categories are removed. Works only when the category is the default one for this product
- Manager update exists now. Run ```php Thelia thelia:update```
- Coupon works now
- Improved tax rule configuration

#2.0.0-beta2

- http://doc.thelia.net is available in beta.
- Increase performance in prod mode.
- Front part (routes and controller) are now a dedicated module.
- allow to create a customer in admin panel
- translation is implemented :
	- I18n directory in template or module.
	- multiple extensions are available. We choose to use php but you can use other.
	- You can translate your template or module from the admin.
- Admin hooks exist. With this hooks, a module can insert code in admin pages
- Admin hooks can be display using SHOW_INCLUDE=1 in your query string and in dev mode (http://doc.thelia.net/en/documentation/modules/hook.html)
- change memory_limit parameter in installation process. 128M is now needed
- assets can be used from template directory and from module
- Product, Category, Folder and Content have a dedicated SEO panel
- Allow to configure store information like email, address, phone number, etc.
- email management : http://doc.thelia.net/en/documentation/templates/emails.html
- "How to contribute ?" see http://doc.thelia.net/en/documentation/contribute.html
-Cache http (use it carefully, default template is not compatible with this cache) :
	- if you don't know http specification, learn it first http://www.w3.org/Protocols/rfc2616/rfc2616.html
	- esi tag integrated, use {render_esi path="http://your-taget.tld/resource"}
	- if no reverse proxy detected, html is render instead of esi tag
	- if you can't install a reverse proxy like varnish, use the HttpCache (just uncomment line 14 in web/index.php file)
	- resources :
		- http://www.mnot.net/cache_docs/ (fr)
		- http://tomayko.com/writings/things-caches-do (en)
		- http://symfony.com/doc/current/book/http_cache.html#http-cache-introduction (en and fr)
