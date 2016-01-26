# oc-angular 




# usage

ocPopup:
 
eventClick: function(calEvent, jsEvent, view) {
            var eventPopup = $ocPopup.show({
                event: jsEvent,
                controller: "taskEventModCtrl",
                resolve: {
                    title: function () {
                        return "Deneme Lan bu "
                    }
                },
                minWidth: 400,
                windowClass: 'edit-modal-window modal-sm',
                templateUrl: _modulePath + '/task/taskevent-mod.html?v=' + Math.random()
            });

            eventPopup.then(function () {
                eventPopup = null;
            });
        }
