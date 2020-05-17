
all under Player.gd(gdscript)

WHAT FUNCTION STARTS AFTER NODE ENTER
# _ready is Called when the node enters the scene tree for the first time.
func _ready():
	print("hello world!")
	pass # Replace with function body.

STEP EVENT
#ini macam step event dalam Gamemaker
disini kau letak perubahan velocity
func _physics_process(delta):

KEYCHECK
boleh cek key press dgn
Input.is_action_pressed("")

cth:
	if Input.is_action_pressed("ui_right"):
		velocity.x = 4










SIMPLE PHASE of movement coding


extends KinematicBody2D

var velocity = Vector2.ZERO
var MAX_SPEED = 50

# Called when the node enters the scene tree for the first time.


  func _physics_process(delta):
  	var input_vector = Vector2.ZERO
  	input_vector.x = Input.get_action_strength("ui_right") - Input.get_action_strength("ui_left")
  	input_vector.y = Input.get_action_strength("ui_down") - Input.get_action_strength("ui_up")
	
	if input_vector != Vector2.ZERO:
		velocity = input_vector
	else:
		velocity = Vector2.ZERO
	move_and_collide(velocity * delta * MAX_SPEED)

