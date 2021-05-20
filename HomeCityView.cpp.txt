#include <windows.h>  // for MS Windows
#include <GL/glut.h>  // GLUT, include glu.h and gl.h
#include<math.h>>
# define PI           3.14159265358979323846

GLfloat rots = 0.0f;
GLfloat rotm = 0.0f;
GLfloat roth = 0.0f;

void Idle()
{
    glutPostRedisplay();//// marks the current window as needing to be redisplayed
}

GLfloat positioncar = 0.0f;
GLfloat speedcar = 0.1f;

void updatecar(int value) {

    if(positioncar >1.2)
        positioncar = -1.2f;

    positioncar += speedcar; //position=position-speed;1-.1=.9

	glutPostRedisplay();


	glutTimerFunc(100, updatecar, 0);
}

GLfloat positioncloud = 0.0f;
GLfloat speedcloud = 0.1f;

void updatecloud(int value) {

    if(positioncloud <-1.2)
        positioncloud = 1.2f;

    positioncloud -= speedcloud; //position=position-speed;1-.1=.9

	glutPostRedisplay();


	glutTimerFunc(300, updatecloud, 0);
}

///////////////////////////////////////////////////////////////////////////////////////////////////////////

void morning() {
	glClearColor(0.0f, 0.0f, 0.0f, 1.0f);
	glClear(GL_COLOR_BUFFER_BIT);
	//glLineWidth(7.5);

		glBegin(GL_QUADS); //background
    glColor4f(0.0f, 1.0f, 1.0f, 1.0f);//light blue
    glVertex2f( -1, -0.13 );
    glColor4f(0.0f, 1.0f, 1.0f, 1.0f);//light blue
    glVertex2f( 1, -0.13 );
    glColor4f(0.0f, 1.0f, 1.0f, 1.0f);//light blue
    glVertex2f( 1, 1 );
    glColor4f(0.0f, 1.0f, 1.0f, 1.0f);//light blue
    glVertex2f( -1, 1 );
    glEnd();

        //bush 1

    GLfloat b1=-.88f; GLfloat bu1=-.13f; GLfloat radiusb1=.15f;

    int i;
    int lineAmount = 100; //# of triangles used to draw circle

    GLfloat twicePib = 1.0f * PI;
    GLfloat twicePi = 2.0f * PI;

    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b1 + (radiusb1 * cos(i *  twicePib / lineAmount)),
                bu1 + (radiusb1 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();

            //bush 2

    GLfloat b2=-.60f; GLfloat bu2=-.13f; GLfloat radiusb2=.15f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b2 + (radiusb2 * cos(i *  twicePib / lineAmount)),
                bu2 + (radiusb2 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();

                //bush 3

    GLfloat b3=-.32f; GLfloat bu3=-.13f; GLfloat radiusb3=.15f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b3 + (radiusb3 * cos(i *  twicePib / lineAmount)),
                bu3 + (radiusb3 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();

                    //bush 4

    GLfloat b4=.30f; GLfloat bu4=-.13f; GLfloat radiusb4=.15f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b4 + (radiusb4 * cos(i *  twicePib / lineAmount)),
                bu4 + (radiusb4 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();


                        //bush 5

    GLfloat b5=.65f; GLfloat bu5=-.13f; GLfloat radiusb5=.15f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b5 + (radiusb5 * cos(i *  twicePib / lineAmount)),
                bu5 + (radiusb5 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();

                           //bush 6

    GLfloat b6=.89f; GLfloat bu6=-.13f; GLfloat radiusb6=.15f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b6 + (radiusb6 * cos(i *  twicePib / lineAmount)),
                bu6 + (radiusb6 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();


	glBegin(GL_QUADS); //house1
    glColor3f( 1, 0, 0 );
    glVertex2f( -0.2, -0.13 );
    glColor3f( 1, 0, 0 );
    glVertex2f( 0.2, -0.13 );
    glColor3f( 1, 0, 0 );
    glVertex2f( 0.2, 0.2 );
    glColor3f( 1, 0, 0 );
    glVertex2f( -0.2, 0.2 );
    glEnd();

    glBegin(GL_TRIANGLES); //house1 roof
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( -0.2, 0.2 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.2, 0.2 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0, 0.4 );
    glEnd();

    glBegin(GL_QUADS); //house1 window1
    glColor3f( 0, 0, 0 );
    glVertex2f( -0.13, 0.06 );
    glColor3f( 0, 0, 0 );
    glVertex2f( -0.06, 0.06 );
    glColor3f( 0, 0, 0 );
    glVertex2f( -0.06, 0.13 );
    glColor3f( 0, 0, 0 );
    glVertex2f( -0.13, 0.13 );
    glEnd();

    glBegin(GL_QUADS); //house1 window2
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.06, 0.06 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.13, 0.06 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.13, 0.13 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.06, 0.13 );
    glEnd();

    glBegin(GL_QUADS); //house1 door
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.1, -0.13 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.2, -0.13 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.2, -0.03 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.1, -0.03 );
    glEnd();

    glBegin(GL_QUADS); //house2
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.3, -0.13 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.6, -0.13 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.6, 0.5 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.3, 0.5 );
    glEnd();


        glBegin(GL_QUADS);//clocktower-----house2extentionforclocktower

    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.3, 0.5 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.6, 0.5 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.6, 0.9 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.3, 0.9 );
    glEnd();


    glBegin(GL_QUADS); //house2 door
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.4, -0.13 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.5, -0.13 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.5, 0.0 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.4, 0.0 );
    glEnd();

    glBegin(GL_QUADS); //house2 windowdesign
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.3, 0.1 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.6, 0.1 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.6, 0.2 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.3, 0.2 );
    glEnd();

    glBegin(GL_QUADS); //house2 window1
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.33, 0.3 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.43, 0.3 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.43, 0.4 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.33, 0.4 );
    glEnd();

    glBegin(GL_QUADS); //house2 window2
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.46, 0.3 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.56, 0.3 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.56, 0.4 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.46, 0.4 );
    glEnd();

    glBegin(GL_QUADS); //flagstand
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.37, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.36, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.36, 0.23 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.37, 0.23 );
    glEnd();

      glBegin(GL_QUADS); //flag
    glColor3f(0.0, 0.1, 0.0);
    glVertex2f( -0.36, 0.13 );
    glColor3f(0.0, 0.1, 0.0);
    glVertex2f( -0.23, 0.13 );
    glColor3f(0.0, 0.1, 0.0);
    glVertex2f( -0.23, 0.23 );
    glColor3f(0.0, 0.1, 0.0);
    glVertex2f( -0.36, 0.23 );
    glEnd();

     glBegin(GL_QUADS); //tree1
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.66, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.63, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.63, 0.1 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.66, 0.1 );
    glEnd();

    glBegin(GL_QUADS); //tree2
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.7, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.73, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.73, 0.1 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.7, 0.1 );
    glEnd();


     glBegin(GL_POLYGON); //leaf
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.66, 0.1 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.8, 0.1 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.76, 0.2 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.83, 0.2 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.73, 0.3 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.63, 0.2 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.7, 0.2 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.66, 0.1 );

    glEnd();

    glBegin(GL_QUADS); //road
    glColor3f(0.1, 0.1, 0.1);
    glVertex2f( -1, -0.6 );
    glColor3f(0.1, 0.1, 0.1);
    glVertex2f( 1, -0.6 );
    glColor3f(0.1, 0.1, 0.1);
    glVertex2f( 1, -0.13 );
    glColor3f(0.1, 0.1, 0.1);
    glVertex2f( -1, -0.13 );
    glEnd();

    //roadmarkers

     glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(-1, -0.33);
	glVertex2f(-0.9, -0.33);
	glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(-0.8, -0.33);
	glVertex2f(-0.7, -0.33);
	glEnd();

	//glTranslatef(-0.6,0)
    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(-0.6, -0.33);
	glVertex2f(-0.5, -0.33);
    glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(-0.4, -0.33);
	glVertex2f(-0.3, -0.33);
    glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(-0.2, -0.33);
	glVertex2f(-0.1, -0.33);
    glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(0.0, -0.33);
	glVertex2f(0.1, -0.33);
    glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(0.2, -0.33);
	glVertex2f(0.3, -0.33);
    glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(0.4, -0.33);
	glVertex2f(0.5, -0.33);
    glEnd();


    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(0.6, -0.33);
	glVertex2f(0.7, -0.33);
    glEnd();

     glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(0.8, -0.33);
	glVertex2f(0.9, -0.33);
    glEnd();

 ////traffic light

    glBegin(GL_QUADS); //lightstand
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.9, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.915, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.915, 0.1 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.9, 0.1 );
    glEnd();


    glBegin(GL_QUADS); //lightsign
    glColor3f(1.0, 1.0, 1.0);
    glVertex2f( 0.86, -0.08 );
    glColor3f(1.0, 1.0, 1.0);
    glVertex2f( 0.96, -0.08 );
    glColor3f(1.0, 1.0, 1.0);
    glVertex2f( 0.96, 0.09);
    glColor3f(1.0, 1.0, 1.0);
    glVertex2f( 0.86, 0.09 );
    glEnd();


    //lightcircle

    //circle1


    GLfloat light1=0.91f; GLfloat light11=-0.05f; GLfloat lightsize =.02f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.1f, 0.0f);//Forest Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                light1 + (lightsize * cos(i *  twicePi / lineAmount)),
                light11 + (lightsize* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

    //circle2


    GLfloat light2=0.91f; GLfloat light22=0.00f;



    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                light2 + (lightsize * cos(i *  twicePi / lineAmount)),
                light22 + (lightsize* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();


    //circle3


    GLfloat light3=0.91f; GLfloat light33=0.05f;



    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                light3 + (lightsize * cos(i *  twicePi / lineAmount)),
                light33 + (lightsize* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

        //flag circle




    GLfloat e=-.3f; GLfloat f=.18f; GLfloat radiusss=.03f;




    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 0.0f, 0.0f, 0.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                e + (radiusss * cos(i *  twicePi / lineAmount)),
                f + (radiusss * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

     //tree1-leaf1

    GLfloat g=-.65f; GLfloat h=.1f; GLfloat radiusssl=.05f;




    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                g + (radiusssl * cos(i *  twicePi / lineAmount)),
                h + (radiusssl * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

     //tree1-leaf2

    GLfloat j=-.68f; GLfloat k=.16f; GLfloat radiusssl2=.05f;




    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                j + (radiusssl2 * cos(i *  twicePi / lineAmount)),
                k + (radiusssl2 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

         //tree1-leaf3

    GLfloat m=-.616f; GLfloat n=.16f; GLfloat radiusssl23=.05f;




    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                m + (radiusssl23 * cos(i *  twicePi / lineAmount)),
                n + (radiusssl23 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

             //tree1-leaf4

    GLfloat o=-.65f; GLfloat p=.23f; GLfloat radiusssl234=.05f;




    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                o + (radiusssl234 * cos(i *  twicePi / lineAmount)),
                p + (radiusssl234 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();




                             //clockshape

    GLfloat clock=0.45; GLfloat clockk=.7f; GLfloat radiusclock=.12f;




    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                clock + (radiusclock * cos(i *  twicePi / lineAmount)),
                clockk + (radiusclock * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

//rotation-bhaviour-second


   glPushMatrix(); //glPushMatrix copies the top matrix and pushes it onto the stack, while glPopMatrix pops the top matrix off the stack
   glTranslatef(0.45,0.7,0);
   glRotatef(rots,0.0,0.0,1.0);

       //katasecond

    glBegin(GL_LINES);
	glColor3f(1, 0, 0.);
	glVertex2f(0.0, 0.0);
	glVertex2f(0.05, 0.09);
	glEnd();
	glLoadIdentity();



    //katahour
//   glBegin(GL_LINES);
//	glColor3f(0, 0, 0.);
//	glVertex2f(0.0, 0.0);
//	glVertex2f(0.4, 0.7);
//    glEnd();

     glPopMatrix();//while glPopMatrix pops the top matrix off the stack

     rots-=0.04f;




     //rotation-bhaviour-minute


   glPushMatrix(); //glPushMatrix copies the top matrix and pushes it onto the stack, while glPopMatrix pops the top matrix off the stack
   glTranslatef(0.45,0.7,0);
   glRotatef(rotm,0.0,0.0,1.0);

    //katamin
    glBegin(GL_LINES);
	glColor3f(0, 0, 0);
	glVertex2f(0.0, 0.0);
	glVertex2f(0.03, 0.05);
	glEnd();
	glLoadIdentity();


     glPopMatrix();//while glPopMatrix pops the top matrix off the stack

     rotm-=0.01f;


          //rotation-bhaviour-hour


   glPushMatrix(); //glPushMatrix copies the top matrix and pushes it onto the stack, while glPopMatrix pops the top matrix off the stack
   glTranslatef(0.45,0.7,0);
   glRotatef(roth,0.0,0.0,1.0);



    //katahour
    glBegin(GL_LINES);
	glColor3f(0, 0, 0);
	glVertex2f(0.0, 0.0);
	glVertex2f(0.018, 0.03);
    glEnd();
    glLoadIdentity();

     glPopMatrix();//while glPopMatrix pops the top matrix off the stack

     roth-=0.008f;


     //trainmaking

         glBegin(GL_QUADS); //road
    glColor3f(0.0f, 1.0f, 0.0f);//Green
    glVertex2f( -1, -0.6 );
    glColor3f(0.0f, 1.0f, 0.0f);//Green
    glVertex2f( 1, -0.6 );
    glColor3f(0.0f, 1.0f, 0.0f);//Green
    glVertex2f( 1, -2);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
    glVertex2f( -1, -2 );
    glEnd();

    //raillines

    glBegin(GL_LINES);//raillines1-1
	glColor3f(0, 0, 0.);
	glVertex2f(-1, -0.91);
	glVertex2f(1, -0.91);
	glEnd();

	glBegin(GL_LINES);//raillines1-2
	glColor3f(0, 0, 0.);
	glVertex2f(-1, -0.90);
	glVertex2f(1, -0.90);
	glEnd();


	 glBegin(GL_LINES);//raillines1-1
	glColor3f(0, 0, 0.);
	glVertex2f(-1, -0.75);
	glVertex2f(1, -0.75);
	glEnd();

	glBegin(GL_LINES);//raillines1-2
	glColor3f(0, 0, 0.);
	glVertex2f(-1, -0.74);
	glVertex2f(1, -0.74);
	glEnd();

	//railbracks

	glBegin(GL_LINES);//railbracks1
	glColor3f(0, 0, 0.);
	glVertex2f(-1.04, -0.91);
	glVertex2f(-0.97, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks2
	glColor3f(0, 0, 0.);
	glVertex2f(-0.97, -0.91);
	glVertex2f(-0.9, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks3
	glColor3f(0, 0, 0.);
	glVertex2f(-0.87, -0.91);
	glVertex2f(-0.8, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks4
	glColor3f(0, 0, 0.);
	glVertex2f(-0.77, -0.91);
	glVertex2f(-0.7, -0.74);
	glEnd();


	glBegin(GL_LINES);//railbracks5
	glColor3f(0, 0, 0.);
	glVertex2f(-0.67, -0.91);
	glVertex2f(-0.6, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks6
	glColor3f(0, 0, 0.);
	glVertex2f(-0.57, -0.91);
	glVertex2f(-0.5, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks7
	glColor3f(0, 0, 0.);
	glVertex2f(-0.47, -0.91);
	glVertex2f(-0.4, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks8
	glColor3f(0, 0, 0.);
	glVertex2f(-0.37, -0.91);
	glVertex2f(-0.3, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks9
	glColor3f(0, 0, 0.);
	glVertex2f(-0.27, -0.91);
	glVertex2f(-0.2, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks10
	glColor3f(0, 0, 0.);
	glVertex2f(-0.17, -0.91);
	glVertex2f(-0.1, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks11
	glColor3f(0, 0, 0.);
	glVertex2f(-0.07, -0.91);
	glVertex2f(0.0, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks12
	glColor3f(0, 0, 0.);
	glVertex2f(0.04, -0.91);
	glVertex2f(0.1, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks13
	glColor3f(0, 0, 0.);
	glVertex2f(0.14, -0.91);
	glVertex2f(0.2, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks14
	glColor3f(0, 0, 0.);
	glVertex2f(0.24, -0.91);
	glVertex2f(0.3, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks15
	glColor3f(0, 0, 0.);
	glVertex2f(0.34, -0.91);
	glVertex2f(0.4, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks16
	glColor3f(0, 0, 0.);
	glVertex2f(0.44, -0.91);
	glVertex2f(0.5, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks17
	glColor3f(0, 0, 0.);
	glVertex2f(0.54, -0.91);
	glVertex2f(0.6, -0.74);
	glEnd();


	glBegin(GL_LINES);//railbracks18
	glColor3f(0, 0, 0.);
	glVertex2f(0.64, -0.91);
	glVertex2f(0.7, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks19
	glColor3f(0, 0, 0.);
	glVertex2f(0.74, -0.91);
	glVertex2f(0.8, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks20
	glColor3f(0, 0, 0.);
	glVertex2f(0.84, -0.91);
	glVertex2f(0.9, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks21
	glColor3f(0, 0, 0.);
	glVertex2f(0.94, -0.91);
	glVertex2f(1, -0.74);
	glEnd();

    glFlush();  // Render now


}


///////////////////////////////////////////////////////////////////////////////////////////////////////


void day() {
	glClearColor(0.0f, 0.0f, 0.0f, 1.0f);
	glClear(GL_COLOR_BUFFER_BIT);
	//glLineWidth(7.5);

		glBegin(GL_QUADS); //background
    glColor4f(0.0f, 1.0f, 1.0f, 1.0f);//light blue
    glVertex2f( -1, -0.13 );
    glColor4f(0.0f, 1.0f, 1.0f, 1.0f);//light blue
    glVertex2f( 1, -0.13 );
    glColor4f(0.0f, 1.0f, 1.0f, 1.0f);//light blue
    glVertex2f( 1, 1 );
    glColor4f(0.0f, 1.0f, 1.0f, 1.0f);//light blue
    glVertex2f( -1, 1 );
    glEnd();

        //bush 1

    GLfloat b1=-.88f; GLfloat bu1=-.13f; GLfloat radiusb1=.15f;

    int i;
    int lineAmount = 100; //# of triangles used to draw circle

    GLfloat twicePib = 1.0f * PI;
    GLfloat twicePi = 2.0f * PI;

    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b1 + (radiusb1 * cos(i *  twicePib / lineAmount)),
                bu1 + (radiusb1 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();

            //bush 2

    GLfloat b2=-.60f; GLfloat bu2=-.13f; GLfloat radiusb2=.15f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b2 + (radiusb2 * cos(i *  twicePib / lineAmount)),
                bu2 + (radiusb2 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();

                //bush 3

    GLfloat b3=-.32f; GLfloat bu3=-.13f; GLfloat radiusb3=.15f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b3 + (radiusb3 * cos(i *  twicePib / lineAmount)),
                bu3 + (radiusb3 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();

                    //bush 4

    GLfloat b4=.30f; GLfloat bu4=-.13f; GLfloat radiusb4=.15f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b4 + (radiusb4 * cos(i *  twicePib / lineAmount)),
                bu4 + (radiusb4 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();

                        //bush 5

    GLfloat b5=.65f; GLfloat bu5=-.13f; GLfloat radiusb5=.15f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b5 + (radiusb5 * cos(i *  twicePib / lineAmount)),
                bu5 + (radiusb5 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();

                           //bush 6

    GLfloat b6=.89f; GLfloat bu6=-.13f; GLfloat radiusb6=.15f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b6 + (radiusb6 * cos(i *  twicePib / lineAmount)),
                bu6 + (radiusb6 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();


    //cloudmovement backwards

    glPushMatrix();
    glTranslatef(positioncloud,0,0);

    //cloudmaking1

    GLfloat q=-.8f; GLfloat r=.45f; GLfloat radiusssl2345=.04f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                q + (radiusssl2345 * cos(i *  twicePi / lineAmount)),
                r + (radiusssl2345 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                 //cloudmaking2

    GLfloat s=-.74f; GLfloat t=.45f; GLfloat radiusssl23456=.04f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                s + (radiusssl23456 * cos(i *  twicePi / lineAmount)),
                t + (radiusssl23456 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                     //cloudmaking3

    GLfloat u=-.68f; GLfloat v=.45f; GLfloat radiusssl234567=.04f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                u + (radiusssl234567 * cos(i *  twicePi / lineAmount)),
                v + (radiusssl234567 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                         //cloudmaking4

    GLfloat u1=-.7f; GLfloat v1=.5f; GLfloat radiusssl2345678=.04f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                u1 + (radiusssl2345678 * cos(i *  twicePi / lineAmount)),
                v1 + (radiusssl2345678 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                                 //cloudmaking5

    GLfloat u12=-.76f; GLfloat v12=.5f; GLfloat radiusssl23456789=.04f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                u12 + (radiusssl23456789 * cos(i *  twicePi / lineAmount)),
                v12 + (radiusssl23456789 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();


    //cloudmaking1-1

    GLfloat cx1=-.4f; GLfloat cy1=.55f; GLfloat c2r1=.04f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                cx1 + (c2r1 * cos(i *  twicePi / lineAmount)),
                cy1 + (c2r1 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                 //cloudmaking2-1

    GLfloat cx2=-.34f; GLfloat cy2=.55f; GLfloat c2r2=.04f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                cx2 + (c2r2 * cos(i *  twicePi / lineAmount)),
                cy2 + (c2r2 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                     //cloudmaking3-1

    GLfloat cx3=-.28f; GLfloat cy3=.55f; GLfloat c2r3=.04f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                cx3 + (c2r3 * cos(i *  twicePi / lineAmount)),
                cy3 + (c2r3 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                         //cloudmaking4-1

    GLfloat cx4=-.3f; GLfloat cy4=.6f; GLfloat c2r4=.04f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                cx4 + (c2r4 * cos(i *  twicePi / lineAmount)),
                cy4 + (c2r4 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                                 //cloudmaking5-1

    GLfloat cx5=-.36f; GLfloat cy5=.6f; GLfloat c2r5=.04f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                cx5 + (c2r5 * cos(i *  twicePi / lineAmount)),
                cy5 + (c2r5 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();


    glPopMatrix();



    //buildings


	glBegin(GL_QUADS); //house1
    glColor3f( 1, 0, 0 );
    glVertex2f( -0.2, -0.13 );
    glColor3f( 1, 0, 0 );
    glVertex2f( 0.2, -0.13 );
    glColor3f( 1, 0, 0 );
    glVertex2f( 0.2, 0.2 );
    glColor3f( 1, 0, 0 );
    glVertex2f( -0.2, 0.2 );
    glEnd();

    glBegin(GL_TRIANGLES); //house1 roof
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( -0.2, 0.2 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.2, 0.2 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0, 0.4 );
    glEnd();

    glBegin(GL_QUADS); //house1 window1
    glColor3f( 0, 0, 0 );
    glVertex2f( -0.13, 0.06 );
    glColor3f( 0, 0, 0 );
    glVertex2f( -0.06, 0.06 );
    glColor3f( 0, 0, 0 );
    glVertex2f( -0.06, 0.13 );
    glColor3f( 0, 0, 0 );
    glVertex2f( -0.13, 0.13 );
    glEnd();

    glBegin(GL_QUADS); //house1 window2
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.06, 0.06 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.13, 0.06 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.13, 0.13 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.06, 0.13 );
    glEnd();

    glBegin(GL_QUADS); //house1 door
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.1, -0.13 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.2, -0.13 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.2, -0.03 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.1, -0.03 );
    glEnd();

    glBegin(GL_QUADS); //house2
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.3, -0.13 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.6, -0.13 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.6, 0.5 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.3, 0.5 );
    glEnd();


    glBegin(GL_QUADS);//clocktower-----house2extentionforclocktower
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.3, 0.5 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.6, 0.5 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.6, 0.9 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.3, 0.9 );
    glEnd();

    glBegin(GL_QUADS); //house2 door
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.4, -0.13 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.5, -0.13 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.5, 0.0 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.4, 0.0 );
    glEnd();

    glBegin(GL_QUADS); //house2 windowdesign
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.3, 0.1 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.6, 0.1 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.6, 0.2 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.3, 0.2 );
    glEnd();

    glBegin(GL_QUADS); //house2 window1
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.33, 0.3 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.43, 0.3 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.43, 0.4 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.33, 0.4 );
    glEnd();

    glBegin(GL_QUADS); //house2 window2
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.46, 0.3 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.56, 0.3 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.56, 0.4 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.46, 0.4 );
    glEnd();

    glBegin(GL_QUADS); //flagstand
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.37, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.36, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.36, 0.23 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.37, 0.23 );
    glEnd();

    glBegin(GL_QUADS); //flag
    glColor3f(0.0, 0.1, 0.0);
    glVertex2f( -0.36, 0.13 );
    glColor3f(0.0, 0.1, 0.0);
    glVertex2f( -0.23, 0.13 );
    glColor3f(0.0, 0.1, 0.0);
    glVertex2f( -0.23, 0.23 );
    glColor3f(0.0, 0.1, 0.0);
    glVertex2f( -0.36, 0.23 );
    glEnd();

    glBegin(GL_QUADS); //tree1
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.66, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.63, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.63, 0.1 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.66, 0.1 );
    glEnd();

    glBegin(GL_QUADS); //tree2
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.7, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.73, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.73, 0.1 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.7, 0.1 );
    glEnd();


    glBegin(GL_POLYGON); //leaf
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.66, 0.1 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.8, 0.1 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.76, 0.2 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.83, 0.2 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.73, 0.3 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.63, 0.2 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.7, 0.2 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.66, 0.1 );
    glEnd();

    glBegin(GL_QUADS); //road
    glColor3f(0.1, 0.1, 0.1);
    glVertex2f( -1, -0.6 );
    glColor3f(0.1, 0.1, 0.1);
    glVertex2f( 1, -0.6 );
    glColor3f(0.1, 0.1, 0.1);
    glVertex2f( 1, -0.13 );
    glColor3f(0.1, 0.1, 0.1);
    glVertex2f( -1, -0.13 );
    glEnd();

    //roadmarkers

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(-1, -0.33);
	glVertex2f(-0.9, -0.33);
	glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(-0.8, -0.33);
	glVertex2f(-0.7, -0.33);
	glEnd();

	//glTranslatef(-0.6,0)
    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(-0.6, -0.33);
	glVertex2f(-0.5, -0.33);
    glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(-0.4, -0.33);
	glVertex2f(-0.3, -0.33);
    glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(-0.2, -0.33);
	glVertex2f(-0.1, -0.33);
    glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(0.0, -0.33);
	glVertex2f(0.1, -0.33);
    glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(0.2, -0.33);
	glVertex2f(0.3, -0.33);
    glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(0.4, -0.33);
	glVertex2f(0.5, -0.33);
    glEnd();


    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(0.6, -0.33);
	glVertex2f(0.7, -0.33);
    glEnd();

     glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(0.8, -0.33);
	glVertex2f(0.9, -0.33);
    glEnd();



    ////traffic light

    glBegin(GL_QUADS); //lightstand
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.9, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.915, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.915, 0.1 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.9, 0.1 );
    glEnd();

    glBegin(GL_QUADS); //lightsign
    glColor3f(1.0, 1.0, 1.0);
    glVertex2f( 0.86, -0.08 );
    glColor3f(1.0, 1.0, 1.0);
    glVertex2f( 0.96, -0.08 );
    glColor3f(1.0, 1.0, 1.0);
    glVertex2f( 0.96, 0.09);
    glColor3f(1.0, 1.0, 1.0);
    glVertex2f( 0.86, 0.09 );
    glEnd();


    //lightcircle

    //circle1

    GLfloat light1=0.91f; GLfloat light11=-0.05f; GLfloat lightsize =.02f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.1f, 0.0f);//Forest Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                light1 + (lightsize * cos(i *  twicePi / lineAmount)),
                light11 + (lightsize* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

    //circle2

    GLfloat light2=0.91f; GLfloat light22=0.00f;

    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                light2 + (lightsize * cos(i *  twicePi / lineAmount)),
                light22 + (lightsize* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();


    //circle3

    GLfloat light3=0.91f; GLfloat light33=0.05f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                light3 + (lightsize * cos(i *  twicePi / lineAmount)),
                light33 + (lightsize* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();





    //car movement

    glPushMatrix();
    glTranslatef(positioncar,0,0);

    glBegin(GL_POLYGON); //car
    glColor3f(0.0, 0.5, 1.0);
    glVertex2f( 0.033, -0.4 );
    glColor3f(0.0, 0.5, 1.0);
    glVertex2f( 0.5, -0.4 );
    glColor3f(0.0, 0.5, 1.0);
    glVertex2f( 0.5, -0.3 );
    glColor3f(0.0, 0.5, 1.0);
    glVertex2f( 0.43, -0.3 );
    glColor3f(0.0, 0.5, 1.0);
    glVertex2f( 0.33, -0.23 );
    glColor3f(0.0, 0.5, 1.0);
    glVertex2f( 0.13, -0.23 );
    glColor3f(0.0, 0.5, 1.0);
    glVertex2f( 0.033, -0.3 );
    glEnd();


    //1 rim

    GLfloat x=.16f; GLfloat y=-.4f; GLfloat radius =.05f;

    //GLfloat radius = 0.8f; //radius

    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                x + (radius * cos(i *  twicePi / lineAmount)),
                y + (radius* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

//2 rim


    GLfloat a=.36f; GLfloat b=-.4f;

    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                a + (radius * cos(i *  twicePi / lineAmount)),
                b + (radius* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();


    glPopMatrix();






/* Handler for window-repaint event. Call back when the window first appears and
whenever the window needs to be re-painted. */


    //sun

    GLfloat c=-.3f; GLfloat d=.8f; GLfloat radiuss=.1f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 0.5f, 0.0f, 0.0f);//orange/brown
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                c + (radiuss * cos(i *  twicePi / lineAmount)),
                d + (radiuss * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

        //flag circle


    GLfloat e=-.3f; GLfloat f=.18f; GLfloat radiusss=.03f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 0.0f, 0.0f, 0.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                e + (radiusss * cos(i *  twicePi / lineAmount)),
                f + (radiusss * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

     //tree1-leaf1

    GLfloat g=-.65f; GLfloat h=.1f; GLfloat radiusssl=.05f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                g + (radiusssl * cos(i *  twicePi / lineAmount)),
                h + (radiusssl * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

     //tree1-leaf2

    GLfloat j=-.68f; GLfloat k=.16f; GLfloat radiusssl2=.05f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                j + (radiusssl2 * cos(i *  twicePi / lineAmount)),
                k + (radiusssl2 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

         //tree1-leaf3

    GLfloat m=-.616f; GLfloat n=.16f; GLfloat radiusssl23=.05f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                m + (radiusssl23 * cos(i *  twicePi / lineAmount)),
                n + (radiusssl23 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

             //tree1-leaf4

    GLfloat o=-.65f; GLfloat p=.23f; GLfloat radiusssl234=.05f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                o + (radiusssl234 * cos(i *  twicePi / lineAmount)),
                p + (radiusssl234 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();


                             //clockshape

    GLfloat clock=0.45; GLfloat clockk=.7f; GLfloat radiusclock=.12f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                clock + (radiusclock * cos(i *  twicePi / lineAmount)),
                clockk + (radiusclock * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

//rotation-bhaviour-second


   glPushMatrix(); //glPushMatrix copies the top matrix and pushes it onto the stack, while glPopMatrix pops the top matrix off the stack
   glTranslatef(0.45,0.7,0);
   glRotatef(rots,0.0,0.0,1.0);

       //katasecond

    glBegin(GL_LINES);
	glColor3f(1, 0, 0.);
	glVertex2f(0.0, 0.0);
	glVertex2f(0.05, 0.09);
	glEnd();
	glLoadIdentity();

    //katahour
//   glBegin(GL_LINES);
//	glColor3f(0, 0, 0.);
//	glVertex2f(0.0, 0.0);
//	glVertex2f(0.4, 0.7);
//    glEnd();

     glPopMatrix();//while glPopMatrix pops the top matrix off the stack

     rots-=0.04f;


     //rotation-bhaviour-minute


   glPushMatrix(); //glPushMatrix copies the top matrix and pushes it onto the stack, while glPopMatrix pops the top matrix off the stack
   glTranslatef(0.45,0.7,0);
   glRotatef(rotm,0.0,0.0,1.0);

    //katamin
    glBegin(GL_LINES);
	glColor3f(0, 0, 0);
	glVertex2f(0.0, 0.0);
	glVertex2f(0.03, 0.05);
	glEnd();
	glLoadIdentity();


     glPopMatrix();//while glPopMatrix pops the top matrix off the stack

     rotm-=0.01f;


    //rotation-bhaviour-hour


   glPushMatrix(); //glPushMatrix copies the top matrix and pushes it onto the stack, while glPopMatrix pops the top matrix off the stack
   glTranslatef(0.45,0.7,0);
   glRotatef(roth,0.0,0.0,1.0);



    //katahour
    glBegin(GL_LINES);
	glColor3f(0, 0, 0);
	glVertex2f(0.0, 0.0);
	glVertex2f(0.018, 0.03);
    glEnd();
    glLoadIdentity();

     glPopMatrix();//while glPopMatrix pops the top matrix off the stack

     roth-=0.008f;


     //trainmaking

    glBegin(GL_QUADS); //road
    glColor3f(0.0f, 1.0f, 0.0f);//Green
    glVertex2f( -1, -0.6 );
    glColor3f(0.0f, 1.0f, 0.0f);//Green
    glVertex2f( 1, -0.6 );
    glColor3f(0.0f, 1.0f, 0.0f);//Green
    glVertex2f( 1, -2);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
    glVertex2f( -1, -2 );
    glEnd();

    //raillines

    glBegin(GL_LINES);//raillines1-1
	glColor3f(0, 0, 0.);
	glVertex2f(-1, -0.91);
	glVertex2f(1, -0.91);
	glEnd();

	glBegin(GL_LINES);//raillines1-2
	glColor3f(0, 0, 0.);
	glVertex2f(-1, -0.90);
	glVertex2f(1, -0.90);
	glEnd();


    glBegin(GL_LINES);//raillines1-1
	glColor3f(0, 0, 0.);
	glVertex2f(-1, -0.75);
	glVertex2f(1, -0.75);
	glEnd();

	glBegin(GL_LINES);//raillines1-2
	glColor3f(0, 0, 0.);
	glVertex2f(-1, -0.74);
	glVertex2f(1, -0.74);
	glEnd();

	//railbracks

	glBegin(GL_LINES);//railbracks1
	glColor3f(0, 0, 0.);
	glVertex2f(-1.04, -0.91);
	glVertex2f(-0.97, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks2
	glColor3f(0, 0, 0.);
	glVertex2f(-0.97, -0.91);
	glVertex2f(-0.9, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks3
	glColor3f(0, 0, 0.);
	glVertex2f(-0.87, -0.91);
	glVertex2f(-0.8, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks4
	glColor3f(0, 0, 0.);
	glVertex2f(-0.77, -0.91);
	glVertex2f(-0.7, -0.74);
	glEnd();


	glBegin(GL_LINES);//railbracks5
	glColor3f(0, 0, 0.);
	glVertex2f(-0.67, -0.91);
	glVertex2f(-0.6, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks6
	glColor3f(0, 0, 0.);
	glVertex2f(-0.57, -0.91);
	glVertex2f(-0.5, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks7
	glColor3f(0, 0, 0.);
	glVertex2f(-0.47, -0.91);
	glVertex2f(-0.4, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks8
	glColor3f(0, 0, 0.);
	glVertex2f(-0.37, -0.91);
	glVertex2f(-0.3, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks9
	glColor3f(0, 0, 0.);
	glVertex2f(-0.27, -0.91);
	glVertex2f(-0.2, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks10
	glColor3f(0, 0, 0.);
	glVertex2f(-0.17, -0.91);
	glVertex2f(-0.1, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks11
	glColor3f(0, 0, 0.);
	glVertex2f(-0.07, -0.91);
	glVertex2f(0.0, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks12
	glColor3f(0, 0, 0.);
	glVertex2f(0.04, -0.91);
	glVertex2f(0.1, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks13
	glColor3f(0, 0, 0.);
	glVertex2f(0.14, -0.91);
	glVertex2f(0.2, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks14
	glColor3f(0, 0, 0.);
	glVertex2f(0.24, -0.91);
	glVertex2f(0.3, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks15
	glColor3f(0, 0, 0.);
	glVertex2f(0.34, -0.91);
	glVertex2f(0.4, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks16
	glColor3f(0, 0, 0.);
	glVertex2f(0.44, -0.91);
	glVertex2f(0.5, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks17
	glColor3f(0, 0, 0.);
	glVertex2f(0.54, -0.91);
	glVertex2f(0.6, -0.74);
	glEnd();


	glBegin(GL_LINES);//railbracks18
	glColor3f(0, 0, 0.);
	glVertex2f(0.64, -0.91);
	glVertex2f(0.7, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks19
	glColor3f(0, 0, 0.);
	glVertex2f(0.74, -0.91);
	glVertex2f(0.8, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks20
	glColor3f(0, 0, 0.);
	glVertex2f(0.84, -0.91);
	glVertex2f(0.9, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks21
	glColor3f(0, 0, 0.);
	glVertex2f(0.94, -0.91);
	glVertex2f(1, -0.74);
	glEnd();


    glFlush();  // Render now


}

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


void night() {
	glClearColor(0.0f, 0.0f, 0.0f, 1.0f);
	glClear(GL_COLOR_BUFFER_BIT);
	//glLineWidth(7.5);

		glBegin(GL_QUADS); //background
    glColor3f(0.0f, 0.0f, 0.0f);//Black
    glVertex2f( -1, -0.13 );
    glColor3f(0.0f, 0.0f, 0.0f);//Black
    glVertex2f( 1, -0.13 );
    glColor3f(0.0f, 0.0f, 0.0f);//Black
    glVertex2f( 1, 1 );
    glColor3f(0.0f, 0.0f, 0.0f);//Black
    glVertex2f( -1, 1 );
    glEnd();

        //bush 1

    GLfloat b1=-.88f; GLfloat bu1=-.13f; GLfloat radiusb1=.15f;

    int i;
    int lineAmount = 100; //# of triangles used to draw circle

    GLfloat twicePib = 1.0f * PI;
    GLfloat twicePi = 2.0f * PI;

    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b1 + (radiusb1 * cos(i *  twicePib / lineAmount)),
                bu1 + (radiusb1 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();

            //bush 2

    GLfloat b2=-.60f; GLfloat bu2=-.13f; GLfloat radiusb2=.15f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b2 + (radiusb2 * cos(i *  twicePib / lineAmount)),
                bu2 + (radiusb2 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();

                //bush 3

    GLfloat b3=-.32f; GLfloat bu3=-.13f; GLfloat radiusb3=.15f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b3 + (radiusb3 * cos(i *  twicePib / lineAmount)),
                bu3 + (radiusb3 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();

                    //bush 4

    GLfloat b4=.30f; GLfloat bu4=-.13f; GLfloat radiusb4=.15f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b4 + (radiusb4 * cos(i *  twicePib / lineAmount)),
                bu4 + (radiusb4 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();

                        //bush 5

    GLfloat b5=.65f; GLfloat bu5=-.13f; GLfloat radiusb5=.15f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b5 + (radiusb5 * cos(i *  twicePib / lineAmount)),
                bu5 + (radiusb5 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();

                           //bush 6

    GLfloat b6=.89f; GLfloat bu6=-.13f; GLfloat radiusb6=.15f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b6 + (radiusb6 * cos(i *  twicePib / lineAmount)),
                bu6 + (radiusb6 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();


    //cloudmovement backwards

    glPushMatrix();
    glTranslatef(positioncloud,0,0);

    //cloudmaking1

    GLfloat q=-.8f; GLfloat r=.45f; GLfloat radiusssl2345=.04f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                q + (radiusssl2345 * cos(i *  twicePi / lineAmount)),
                r + (radiusssl2345 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                 //cloudmaking2

    GLfloat s=-.74f; GLfloat t=.45f; GLfloat radiusssl23456=.04f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                s + (radiusssl23456 * cos(i *  twicePi / lineAmount)),
                t + (radiusssl23456 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                     //cloudmaking3

    GLfloat u=-.68f; GLfloat v=.45f; GLfloat radiusssl234567=.04f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                u + (radiusssl234567 * cos(i *  twicePi / lineAmount)),
                v + (radiusssl234567 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                         //cloudmaking4

    GLfloat u1=-.7f; GLfloat v1=.5f; GLfloat radiusssl2345678=.04f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                u1 + (radiusssl2345678 * cos(i *  twicePi / lineAmount)),
                v1 + (radiusssl2345678 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                                 //cloudmaking5

    GLfloat u12=-.76f; GLfloat v12=.5f; GLfloat radiusssl23456789=.04f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                u12 + (radiusssl23456789 * cos(i *  twicePi / lineAmount)),
                v12 + (radiusssl23456789 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();


    //cloudmaking1-1

    GLfloat cx1=-.4f; GLfloat cy1=.55f; GLfloat c2r1=.04f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                cx1 + (c2r1 * cos(i *  twicePi / lineAmount)),
                cy1 + (c2r1 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                 //cloudmaking2-1

    GLfloat cx2=-.34f; GLfloat cy2=.55f; GLfloat c2r2=.04f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                cx2 + (c2r2 * cos(i *  twicePi / lineAmount)),
                cy2 + (c2r2 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                     //cloudmaking3-1

    GLfloat cx3=-.28f; GLfloat cy3=.55f; GLfloat c2r3=.04f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                cx3 + (c2r3 * cos(i *  twicePi / lineAmount)),
                cy3 + (c2r3 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                         //cloudmaking4-1

    GLfloat cx4=-.3f; GLfloat cy4=.6f; GLfloat c2r4=.04f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                cx4 + (c2r4 * cos(i *  twicePi / lineAmount)),
                cy4 + (c2r4 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                                 //cloudmaking5-1

    GLfloat cx5=-.36f; GLfloat cy5=.6f; GLfloat c2r5=.04f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                cx5 + (c2r5 * cos(i *  twicePi / lineAmount)),
                cy5 + (c2r5 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();


    glPopMatrix();



    //buildings


	glBegin(GL_QUADS); //house1
    glColor3f( 1, 0, 0 );
    glVertex2f( -0.2, -0.13 );
    glColor3f( 1, 0, 0 );
    glVertex2f( 0.2, -0.13 );
    glColor3f( 1, 0, 0 );
    glVertex2f( 0.2, 0.2 );
    glColor3f( 1, 0, 0 );
    glVertex2f( -0.2, 0.2 );
    glEnd();

    glBegin(GL_TRIANGLES); //house1 roof
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( -0.2, 0.2 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.2, 0.2 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0, 0.4 );
    glEnd();

    glBegin(GL_QUADS); //house1 window1
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( -0.13, 0.06 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( -0.06, 0.06 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( -0.06, 0.13 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( -0.13, 0.13 );
    glEnd();

    glBegin(GL_QUADS); //house1 window2
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.06, 0.06 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.13, 0.06 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.13, 0.13 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.06, 0.13 );
    glEnd();

    glBegin(GL_QUADS); //house1 door
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.1, -0.13 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.2, -0.13 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.2, -0.03 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.1, -0.03 );
    glEnd();

    glBegin(GL_QUADS); //house2
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.3, -0.13 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.6, -0.13 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.6, 0.5 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.3, 0.5 );
    glEnd();


    glBegin(GL_QUADS);//clocktower-----house2extentionforclocktower
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.3, 0.5 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.6, 0.5 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.6, 0.9 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.3, 0.9 );
    glEnd();

    glBegin(GL_QUADS); //house2 door
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.4, -0.13 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.5, -0.13 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.5, 0.0 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.4, 0.0 );
    glEnd();

    glBegin(GL_QUADS); //house2 windowdesign
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.3, 0.1 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.6, 0.1 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.6, 0.2 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.3, 0.2 );
    glEnd();

    glBegin(GL_QUADS); //house2 window1
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.33, 0.3 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.43, 0.3 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.43, 0.4 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.33, 0.4 );
    glEnd();

    glBegin(GL_QUADS); //house2 window2
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.46, 0.3 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.56, 0.3 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.56, 0.4 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.46, 0.4 );
    glEnd();

    glBegin(GL_QUADS); //flagstand
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.37, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.36, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.36, 0.23 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.37, 0.23 );
    glEnd();


    glBegin(GL_QUADS); //tree1
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.66, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.63, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.63, 0.1 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.66, 0.1 );
    glEnd();

    glBegin(GL_QUADS); //tree2
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.7, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.73, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.73, 0.1 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.7, 0.1 );
    glEnd();


    glBegin(GL_POLYGON); //leaf
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.66, 0.1 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.8, 0.1 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.76, 0.2 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.83, 0.2 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.73, 0.3 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.63, 0.2 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.7, 0.2 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.66, 0.1 );
    glEnd();

    glBegin(GL_QUADS); //road
    glColor3f(0.1, 0.1, 0.1);
    glVertex2f( -1, -0.6 );
    glColor3f(0.1, 0.1, 0.1);
    glVertex2f( 1, -0.6 );
    glColor3f(0.1, 0.1, 0.1);
    glVertex2f( 1, -0.13 );
    glColor3f(0.1, 0.1, 0.1);
    glVertex2f( -1, -0.13 );
    glEnd();

    //roadmarkers

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(-1, -0.33);
	glVertex2f(-0.9, -0.33);
	glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(-0.8, -0.33);
	glVertex2f(-0.7, -0.33);
	glEnd();

	//glTranslatef(-0.6,0)
    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(-0.6, -0.33);
	glVertex2f(-0.5, -0.33);
    glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(-0.4, -0.33);
	glVertex2f(-0.3, -0.33);
    glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(-0.2, -0.33);
	glVertex2f(-0.1, -0.33);
    glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(0.0, -0.33);
	glVertex2f(0.1, -0.33);
    glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(0.2, -0.33);
	glVertex2f(0.3, -0.33);
    glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(0.4, -0.33);
	glVertex2f(0.5, -0.33);
    glEnd();


    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(0.6, -0.33);
	glVertex2f(0.7, -0.33);
    glEnd();

     glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(0.8, -0.33);
	glVertex2f(0.9, -0.33);
    glEnd();



    ////traffic light

    glBegin(GL_QUADS); //lightstand
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.9, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.915, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.915, 0.1 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.9, 0.1 );
    glEnd();

    glBegin(GL_QUADS); //lightsign
    glColor3f(1.0, 1.0, 1.0);
    glVertex2f( 0.86, -0.08 );
    glColor3f(1.0, 1.0, 1.0);
    glVertex2f( 0.96, -0.08 );
    glColor3f(1.0, 1.0, 1.0);
    glVertex2f( 0.96, 0.09);
    glColor3f(1.0, 1.0, 1.0);
    glVertex2f( 0.86, 0.09 );
    glEnd();


    //lightcircle

    //circle1

    GLfloat light1=0.91f; GLfloat light11=-0.05f; GLfloat lightsize =.02f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.1f, 0.0f);//Forest Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                light1 + (lightsize * cos(i *  twicePi / lineAmount)),
                light11 + (lightsize* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

    //circle2

    GLfloat light2=0.91f; GLfloat light22=0.00f;

    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                light2 + (lightsize * cos(i *  twicePi / lineAmount)),
                light22 + (lightsize* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();


    //circle3

    GLfloat light3=0.91f; GLfloat light33=0.05f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                light3 + (lightsize * cos(i *  twicePi / lineAmount)),
                light33 + (lightsize* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();





    //car movement

    glPushMatrix();
    glTranslatef(positioncar,0,0);

    glBegin(GL_POLYGON); //car
    glColor3f(0.0, 0.5, 1.0);
    glVertex2f( 0.033, -0.4 );
    glColor3f(0.0, 0.5, 1.0);
    glVertex2f( 0.5, -0.4 );
    glColor3f(0.0, 0.5, 1.0);
    glVertex2f( 0.5, -0.3 );
    glColor3f(0.0, 0.5, 1.0);
    glVertex2f( 0.43, -0.3 );
    glColor3f(0.0, 0.5, 1.0);
    glVertex2f( 0.33, -0.23 );
    glColor3f(0.0, 0.5, 1.0);
    glVertex2f( 0.13, -0.23 );
    glColor3f(0.0, 0.5, 1.0);
    glVertex2f( 0.033, -0.3 );
    glEnd();

    glBegin(GL_TRIANGLES); //carlight
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.8, -0.5 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.8, -0.2 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.43, -0.34 );
    glEnd();


    //1 rim

    GLfloat x=.16f; GLfloat y=-.4f; GLfloat radius =.05f;

    //GLfloat radius = 0.8f; //radius

    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                x + (radius * cos(i *  twicePi / lineAmount)),
                y + (radius* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

//2 rim


    GLfloat a=.36f; GLfloat b=-.4f;

    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                a + (radius * cos(i *  twicePi / lineAmount)),
                b + (radius* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();


    glPopMatrix();






/* Handler for window-repaint event. Call back when the window first appears and
whenever the window needs to be re-painted. */


    //sun

    GLfloat c=-.3f; GLfloat d=.8f; GLfloat radiuss=.1f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 0.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                c + (radiuss * cos(i *  twicePi / lineAmount)),
                d + (radiuss * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();


     //tree1-leaf1

    GLfloat g=-.65f; GLfloat h=.1f; GLfloat radiusssl=.05f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                g + (radiusssl * cos(i *  twicePi / lineAmount)),
                h + (radiusssl * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

     //tree1-leaf2

    GLfloat j=-.68f; GLfloat k=.16f; GLfloat radiusssl2=.05f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                j + (radiusssl2 * cos(i *  twicePi / lineAmount)),
                k + (radiusssl2 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

         //tree1-leaf3

    GLfloat m=-.616f; GLfloat n=.16f; GLfloat radiusssl23=.05f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                m + (radiusssl23 * cos(i *  twicePi / lineAmount)),
                n + (radiusssl23 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

             //tree1-leaf4

    GLfloat o=-.65f; GLfloat p=.23f; GLfloat radiusssl234=.05f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                o + (radiusssl234 * cos(i *  twicePi / lineAmount)),
                p + (radiusssl234 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();


                             //clockshape

    GLfloat clock=0.45; GLfloat clockk=.7f; GLfloat radiusclock=.12f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                clock + (radiusclock * cos(i *  twicePi / lineAmount)),
                clockk + (radiusclock * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

//rotation-bhaviour-second


   glPushMatrix(); //glPushMatrix copies the top matrix and pushes it onto the stack, while glPopMatrix pops the top matrix off the stack
   glTranslatef(0.45,0.7,0);
   glRotatef(rots,0.0,0.0,1.0);

       //katasecond

    glBegin(GL_LINES);
	glColor3f(1, 0, 0.);
	glVertex2f(0.0, 0.0);
	glVertex2f(0.05, 0.09);
	glEnd();
	glLoadIdentity();

    //katahour
//   glBegin(GL_LINES);
//	glColor3f(0, 0, 0.);
//	glVertex2f(0.0, 0.0);
//	glVertex2f(0.4, 0.7);
//    glEnd();

     glPopMatrix();//while glPopMatrix pops the top matrix off the stack

     rots-=0.04f;


     //rotation-bhaviour-minute


   glPushMatrix(); //glPushMatrix copies the top matrix and pushes it onto the stack, while glPopMatrix pops the top matrix off the stack
   glTranslatef(0.45,0.7,0);
   glRotatef(rotm,0.0,0.0,1.0);

    //katamin
    glBegin(GL_LINES);
	glColor3f(0, 0, 0);
	glVertex2f(0.0, 0.0);
	glVertex2f(0.03, 0.05);
	glEnd();
	glLoadIdentity();


     glPopMatrix();//while glPopMatrix pops the top matrix off the stack

     rotm-=0.01f;


    //rotation-bhaviour-hour


   glPushMatrix(); //glPushMatrix copies the top matrix and pushes it onto the stack, while glPopMatrix pops the top matrix off the stack
   glTranslatef(0.45,0.7,0);
   glRotatef(roth,0.0,0.0,1.0);



    //katahour
    glBegin(GL_LINES);
	glColor3f(0, 0, 0);
	glVertex2f(0.0, 0.0);
	glVertex2f(0.018, 0.03);
    glEnd();
    glLoadIdentity();

     glPopMatrix();//while glPopMatrix pops the top matrix off the stack

     roth-=0.008f;


     //trainmaking

    glBegin(GL_QUADS); //road
    glColor3f(0.0f, 1.0f, 0.0f);//Green
    glVertex2f( -1, -0.6 );
    glColor3f(0.0f, 1.0f, 0.0f);//Green
    glVertex2f( 1, -0.6 );
    glColor3f(0.0f, 1.0f, 0.0f);//Green
    glVertex2f( 1, -2);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
    glVertex2f( -1, -2 );
    glEnd();

    //raillines

    glBegin(GL_LINES);//raillines1-1
	glColor3f(0, 0, 0.);
	glVertex2f(-1, -0.91);
	glVertex2f(1, -0.91);
	glEnd();

	glBegin(GL_LINES);//raillines1-2
	glColor3f(0, 0, 0.);
	glVertex2f(-1, -0.90);
	glVertex2f(1, -0.90);
	glEnd();


    glBegin(GL_LINES);//raillines1-1
	glColor3f(0, 0, 0.);
	glVertex2f(-1, -0.75);
	glVertex2f(1, -0.75);
	glEnd();

	glBegin(GL_LINES);//raillines1-2
	glColor3f(0, 0, 0.);
	glVertex2f(-1, -0.74);
	glVertex2f(1, -0.74);
	glEnd();

	//railbracks

	glBegin(GL_LINES);//railbracks1
	glColor3f(0, 0, 0.);
	glVertex2f(-1.04, -0.91);
	glVertex2f(-0.97, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks2
	glColor3f(0, 0, 0.);
	glVertex2f(-0.97, -0.91);
	glVertex2f(-0.9, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks3
	glColor3f(0, 0, 0.);
	glVertex2f(-0.87, -0.91);
	glVertex2f(-0.8, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks4
	glColor3f(0, 0, 0.);
	glVertex2f(-0.77, -0.91);
	glVertex2f(-0.7, -0.74);
	glEnd();


	glBegin(GL_LINES);//railbracks5
	glColor3f(0, 0, 0.);
	glVertex2f(-0.67, -0.91);
	glVertex2f(-0.6, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks6
	glColor3f(0, 0, 0.);
	glVertex2f(-0.57, -0.91);
	glVertex2f(-0.5, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks7
	glColor3f(0, 0, 0.);
	glVertex2f(-0.47, -0.91);
	glVertex2f(-0.4, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks8
	glColor3f(0, 0, 0.);
	glVertex2f(-0.37, -0.91);
	glVertex2f(-0.3, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks9
	glColor3f(0, 0, 0.);
	glVertex2f(-0.27, -0.91);
	glVertex2f(-0.2, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks10
	glColor3f(0, 0, 0.);
	glVertex2f(-0.17, -0.91);
	glVertex2f(-0.1, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks11
	glColor3f(0, 0, 0.);
	glVertex2f(-0.07, -0.91);
	glVertex2f(0.0, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks12
	glColor3f(0, 0, 0.);
	glVertex2f(0.04, -0.91);
	glVertex2f(0.1, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks13
	glColor3f(0, 0, 0.);
	glVertex2f(0.14, -0.91);
	glVertex2f(0.2, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks14
	glColor3f(0, 0, 0.);
	glVertex2f(0.24, -0.91);
	glVertex2f(0.3, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks15
	glColor3f(0, 0, 0.);
	glVertex2f(0.34, -0.91);
	glVertex2f(0.4, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks16
	glColor3f(0, 0, 0.);
	glVertex2f(0.44, -0.91);
	glVertex2f(0.5, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks17
	glColor3f(0, 0, 0.);
	glVertex2f(0.54, -0.91);
	glVertex2f(0.6, -0.74);
	glEnd();


	glBegin(GL_LINES);//railbracks18
	glColor3f(0, 0, 0.);
	glVertex2f(0.64, -0.91);
	glVertex2f(0.7, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks19
	glColor3f(0, 0, 0.);
	glVertex2f(0.74, -0.91);
	glVertex2f(0.8, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks20
	glColor3f(0, 0, 0.);
	glVertex2f(0.84, -0.91);
	glVertex2f(0.9, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks21
	glColor3f(0, 0, 0.);
	glVertex2f(0.94, -0.91);
	glVertex2f(1, -0.74);
	glEnd();


    glFlush();  // Render now


}


///////////////////////////////////////////////////////////////////////////////////////////////////////////////


void traffic() {
	glClearColor(0.0f, 0.0f, 0.0f, 1.0f);
	glClear(GL_COLOR_BUFFER_BIT);
	//glLineWidth(7.5);

		glBegin(GL_QUADS); //background
    glColor3f(0.0f, 0.0f, 0.0f);//Black
    glVertex2f( -1, -0.13 );
    glColor3f(0.0f, 0.0f, 0.0f);//Black
    glVertex2f( 1, -0.13 );
    glColor3f(0.0f, 0.0f, 0.0f);//Black
    glVertex2f( 1, 1 );
    glColor3f(0.0f, 0.0f, 0.0f);//Black
    glVertex2f( -1, 1 );
    glEnd();

        //bush 1

    GLfloat b1=-.88f; GLfloat bu1=-.13f; GLfloat radiusb1=.15f;

    int i;
    int lineAmount = 100; //# of triangles used to draw circle

    GLfloat twicePib = 1.0f * PI;
    GLfloat twicePi = 2.0f * PI;

    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b1 + (radiusb1 * cos(i *  twicePib / lineAmount)),
                bu1 + (radiusb1 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();

            //bush 2

    GLfloat b2=-.60f; GLfloat bu2=-.13f; GLfloat radiusb2=.15f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b2 + (radiusb2 * cos(i *  twicePib / lineAmount)),
                bu2 + (radiusb2 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();

                //bush 3

    GLfloat b3=-.32f; GLfloat bu3=-.13f; GLfloat radiusb3=.15f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b3 + (radiusb3 * cos(i *  twicePib / lineAmount)),
                bu3 + (radiusb3 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();

                    //bush 4

    GLfloat b4=.30f; GLfloat bu4=-.13f; GLfloat radiusb4=.15f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b4 + (radiusb4 * cos(i *  twicePib / lineAmount)),
                bu4 + (radiusb4 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();


                        //bush 5

    GLfloat b5=.65f; GLfloat bu5=-.13f; GLfloat radiusb5=.15f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b5 + (radiusb5 * cos(i *  twicePib / lineAmount)),
                bu5 + (radiusb5 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();

                           //bush 6

    GLfloat b6=.89f; GLfloat bu6=-.13f; GLfloat radiusb6=.15f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                b6 + (radiusb6 * cos(i *  twicePib / lineAmount)),
                bu6 + (radiusb6 * sin(i * twicePib / lineAmount))
            );
        }
    glEnd();



    //cloudmovement backwards

    glPushMatrix();
    glTranslatef(positioncloud,0,0);

    //cloudmaking1

    GLfloat q=-.8f; GLfloat r=.45f; GLfloat radiusssl2345=.04f;




    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                q + (radiusssl2345 * cos(i *  twicePi / lineAmount)),
                r + (radiusssl2345 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                 //cloudmaking2

    GLfloat s=-.74f; GLfloat t=.45f; GLfloat radiusssl23456=.04f;




    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                s + (radiusssl23456 * cos(i *  twicePi / lineAmount)),
                t + (radiusssl23456 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                     //cloudmaking3

    GLfloat u=-.68f; GLfloat v=.45f; GLfloat radiusssl234567=.04f;




    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                u + (radiusssl234567 * cos(i *  twicePi / lineAmount)),
                v + (radiusssl234567 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                         //cloudmaking4

    GLfloat u1=-.7f; GLfloat v1=.5f; GLfloat radiusssl2345678=.04f;




    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                u1 + (radiusssl2345678 * cos(i *  twicePi / lineAmount)),
                v1 + (radiusssl2345678 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                                 //cloudmaking5

    GLfloat u12=-.76f; GLfloat v12=.5f; GLfloat radiusssl23456789=.04f;




    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                u12 + (radiusssl23456789 * cos(i *  twicePi / lineAmount)),
                v12 + (radiusssl23456789 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();



    //cloudmaking1-1

    GLfloat cx1=-.4f; GLfloat cy1=.55f; GLfloat c2r1=.04f;




    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                cx1 + (c2r1 * cos(i *  twicePi / lineAmount)),
                cy1 + (c2r1 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                 //cloudmaking2-1

    GLfloat cx2=-.34f; GLfloat cy2=.55f; GLfloat c2r2=.04f;




    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                cx2 + (c2r2 * cos(i *  twicePi / lineAmount)),
                cy2 + (c2r2 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                     //cloudmaking3-1

    GLfloat cx3=-.28f; GLfloat cy3=.55f; GLfloat c2r3=.04f;




    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                cx3 + (c2r3 * cos(i *  twicePi / lineAmount)),
                cy3 + (c2r3 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                         //cloudmaking4-1

    GLfloat cx4=-.3f; GLfloat cy4=.6f; GLfloat c2r4=.04f;




    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                cx4 + (c2r4 * cos(i *  twicePi / lineAmount)),
                cy4 + (c2r4 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

                                 //cloudmaking5-1

    GLfloat cx5=-.36f; GLfloat cy5=.6f; GLfloat c2r5=.04f;




    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                cx5 + (c2r5 * cos(i *  twicePi / lineAmount)),
                cy5 + (c2r5 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();


    glPopMatrix();


	glBegin(GL_QUADS); //house1
    glColor3f( 1, 0, 0 );
    glVertex2f( -0.2, -0.13 );
    glColor3f( 1, 0, 0 );
    glVertex2f( 0.2, -0.13 );
    glColor3f( 1, 0, 0 );
    glVertex2f( 0.2, 0.2 );
    glColor3f( 1, 0, 0 );
    glVertex2f( -0.2, 0.2 );
    glEnd();

    glBegin(GL_TRIANGLES); //house1 roof
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( -0.2, 0.2 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.2, 0.2 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0, 0.4 );
    glEnd();

    glBegin(GL_QUADS); //house1 window1
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( -0.13, 0.06 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( -0.06, 0.06 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( -0.06, 0.13 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( -0.13, 0.13 );
    glEnd();

    glBegin(GL_QUADS); //house1 window2
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.06, 0.06 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.13, 0.06 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.13, 0.13 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.06, 0.13 );
    glEnd();

    glBegin(GL_QUADS); //house1 door
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.1, -0.13 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.2, -0.13 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.2, -0.03 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.1, -0.03 );
    glEnd();

    glBegin(GL_QUADS); //house2
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.3, -0.13 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.6, -0.13 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.6, 0.5 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.3, 0.5 );
    glEnd();


        glBegin(GL_QUADS);//clocktower-----house2extentionforclocktower

    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.3, 0.5 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.6, 0.5 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.6, 0.9 );
    glColor3f(0.5, 0.5, 0.5);//Violet
    glVertex2f( 0.3, 0.9 );
    glEnd();


    glBegin(GL_QUADS); //house2 door
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.4, -0.13 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.5, -0.13 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.5, 0.0 );
    glColor3f( 0, 0, 0 );
    glVertex2f( 0.4, 0.0 );
    glEnd();

    glBegin(GL_QUADS); //house2 windowdesign
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.3, 0.1 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.6, 0.1 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.6, 0.2 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.3, 0.2 );
    glEnd();

    glBegin(GL_QUADS); //house2 window1
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.33, 0.3 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.43, 0.3 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.43, 0.4 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.33, 0.4 );
    glEnd();

    glBegin(GL_QUADS); //house2 window2
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.46, 0.3 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.56, 0.3 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.56, 0.4 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.46, 0.4 );
    glEnd();

    glBegin(GL_QUADS); //flagstand
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.37, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.36, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.36, 0.23 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.37, 0.23 );
    glEnd();


     glBegin(GL_QUADS); //tree1
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.66, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.63, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.63, 0.1 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( -0.66, 0.1 );
    glEnd();

    glBegin(GL_QUADS); //tree2
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.7, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.73, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.73, 0.1 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.7, 0.1 );
    glEnd();


     glBegin(GL_POLYGON); //leaf
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.66, 0.1 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.8, 0.1 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.76, 0.2 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.83, 0.2 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.73, 0.3 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.63, 0.2 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.7, 0.2 );
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
    glVertex2f( 0.66, 0.1 );

    glEnd();

    glBegin(GL_QUADS); //road
    glColor3f(0.1, 0.1, 0.1);
    glVertex2f( -1, -0.6 );
    glColor3f(0.1, 0.1, 0.1);
    glVertex2f( 1, -0.6 );
    glColor3f(0.1, 0.1, 0.1);
    glVertex2f( 1, -0.13 );
    glColor3f(0.1, 0.1, 0.1);
    glVertex2f( -1, -0.13 );
    glEnd();

    //roadmarkers

     glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(-1, -0.33);
	glVertex2f(-0.9, -0.33);
	glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(-0.8, -0.33);
	glVertex2f(-0.7, -0.33);
	glEnd();

	//glTranslatef(-0.6,0)
    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(-0.6, -0.33);
	glVertex2f(-0.5, -0.33);
    glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(-0.4, -0.33);
	glVertex2f(-0.3, -0.33);
    glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(-0.2, -0.33);
	glVertex2f(-0.1, -0.33);
    glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(0.0, -0.33);
	glVertex2f(0.1, -0.33);
    glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(0.2, -0.33);
	glVertex2f(0.3, -0.33);
    glEnd();

    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(0.4, -0.33);
	glVertex2f(0.5, -0.33);
    glEnd();


    glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(0.6, -0.33);
	glVertex2f(0.7, -0.33);
    glEnd();

     glBegin(GL_LINES);
	glColor3f(1, 1, 1.);
	glVertex2f(0.8, -0.33);
	glVertex2f(0.9, -0.33);
    glEnd();

 ////traffic light

    glBegin(GL_QUADS); //lightstand
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.9, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.915, -0.13 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.915, 0.1 );
    glColor3f(0.1, 0.0, 0.0);
    glVertex2f( 0.9, 0.1 );
    glEnd();


    glBegin(GL_QUADS); //lightsign
    glColor3f(1.0, 1.0, 1.0);
    glVertex2f( 0.86, -0.08 );
    glColor3f(1.0, 1.0, 1.0);
    glVertex2f( 0.96, -0.08 );
    glColor3f(1.0, 1.0, 1.0);
    glVertex2f( 0.96, 0.09);
    glColor3f(1.0, 1.0, 1.0);
    glVertex2f( 0.86, 0.09 );
    glEnd();





    //lightcircle

    //circle1



    GLfloat light1=0.91f; GLfloat light11=-0.05f; GLfloat lightsize =.02f;


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                light1 + (lightsize * cos(i *  twicePi / lineAmount)),
                light11 + (lightsize* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

    //circle2



    GLfloat light2=0.91f; GLfloat light22=0.00f;



    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                light2 + (lightsize * cos(i *  twicePi / lineAmount)),
                light22 + (lightsize* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();


    //circle3



    GLfloat light3=0.91f; GLfloat light33=0.05f;



    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 0.0f, 0.0f, 0.0f);//red
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                light3 + (lightsize * cos(i *  twicePi / lineAmount)),
                light33 + (lightsize* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();



    //car movement

    glBegin(GL_POLYGON); //car
    glColor3f(0.0, 0.5, 1.0);
    glVertex2f( 0.033, -0.4 );
    glColor3f(0.0, 0.5, 1.0);
    glVertex2f( 0.5, -0.4 );
    glColor3f(0.0, 0.5, 1.0);
    glVertex2f( 0.5, -0.3 );
    glColor3f(0.0, 0.5, 1.0);
    glVertex2f( 0.43, -0.3 );
    glColor3f(0.0, 0.5, 1.0);
    glVertex2f( 0.33, -0.23 );
    glColor3f(0.0, 0.5, 1.0);
    glVertex2f( 0.13, -0.23 );
    glColor3f(0.0, 0.5, 1.0);
    glVertex2f( 0.033, -0.3 );
    glEnd();

    glBegin(GL_TRIANGLES); //carlight
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.8, -0.5 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.8, -0.2 );
    glColor3f(1, 1.0, 0.0);//yellow
    glVertex2f( 0.43, -0.34 );
    glEnd();

    //1 rim



    GLfloat x=.16f; GLfloat y=-.4f; GLfloat radius =.05f;



    //GLfloat radius = 0.8f; //radius


    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                x + (radius * cos(i *  twicePi / lineAmount)),
                y + (radius* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

//2 rim


    GLfloat a=.36f; GLfloat b=-.4f;




    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                a + (radius * cos(i *  twicePi / lineAmount)),
                b + (radius* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();





/* Handler for window-repaint event. Call back when the window first appears and
whenever the window needs to be re-painted. */


    //sun


    GLfloat c=-.3f; GLfloat d=.8f; GLfloat radiuss=.1f;


    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 0.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                c + (radiuss * cos(i *  twicePi / lineAmount)),
                d + (radiuss * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();


     //tree1-leaf1

    GLfloat g=-.65f; GLfloat h=.1f; GLfloat radiusssl=.05f;



    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                g + (radiusssl * cos(i *  twicePi / lineAmount)),
                h + (radiusssl * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

     //tree1-leaf2

    GLfloat j=-.68f; GLfloat k=.16f; GLfloat radiusssl2=.05f;




    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                j + (radiusssl2 * cos(i *  twicePi / lineAmount)),
                k + (radiusssl2 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

         //tree1-leaf3

    GLfloat m=-.616f; GLfloat n=.16f; GLfloat radiusssl23=.05f;




    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                m + (radiusssl23 * cos(i *  twicePi / lineAmount)),
                n + (radiusssl23 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

             //tree1-leaf4

    GLfloat o=-.65f; GLfloat p=.23f; GLfloat radiusssl234=.05f;




    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.5f, 0.0f);//Forest Green
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                o + (radiusssl234 * cos(i *  twicePi / lineAmount)),
                p + (radiusssl234 * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();




                             //clockshape

    GLfloat clock=0.45; GLfloat clockk=.7f; GLfloat radiusclock=.12f;




    glBegin(GL_TRIANGLE_FAN);
    glColor4f(1.0f, 1.0f, 1.0f, 1.0f);//white
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                clock + (radiusclock * cos(i *  twicePi / lineAmount)),
                clockk + (radiusclock * sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

//rotation-bhaviour-second


   glPushMatrix(); //glPushMatrix copies the top matrix and pushes it onto the stack, while glPopMatrix pops the top matrix off the stack
   glTranslatef(0.45,0.7,0);
   glRotatef(rots,0.0,0.0,1.0);

       //katasecond

    glBegin(GL_LINES);
	glColor3f(1, 0, 0.);
	glVertex2f(0.0, 0.0);
	glVertex2f(0.05, 0.09);
	glEnd();
	glLoadIdentity();



    //katahour
//   glBegin(GL_LINES);
//	glColor3f(0, 0, 0.);
//	glVertex2f(0.0, 0.0);
//	glVertex2f(0.4, 0.7);
//    glEnd();

     glPopMatrix();//while glPopMatrix pops the top matrix off the stack

     rots-=0.04f;




     //rotation-bhaviour-minute


   glPushMatrix(); //glPushMatrix copies the top matrix and pushes it onto the stack, while glPopMatrix pops the top matrix off the stack
   glTranslatef(0.45,0.7,0);
   glRotatef(rotm,0.0,0.0,1.0);

    //katamin
    glBegin(GL_LINES);
	glColor3f(0, 0, 0);
	glVertex2f(0.0, 0.0);
	glVertex2f(0.03, 0.05);
	glEnd();
	glLoadIdentity();


     glPopMatrix();//while glPopMatrix pops the top matrix off the stack

     rotm-=0.01f;


          //rotation-bhaviour-hour


   glPushMatrix(); //glPushMatrix copies the top matrix and pushes it onto the stack, while glPopMatrix pops the top matrix off the stack
   glTranslatef(0.45,0.7,0);
   glRotatef(roth,0.0,0.0,1.0);



    //katahour
    glBegin(GL_LINES);
	glColor3f(0, 0, 0);
	glVertex2f(0.0, 0.0);
	glVertex2f(0.018, 0.03);
    glEnd();
    glLoadIdentity();

     glPopMatrix();//while glPopMatrix pops the top matrix off the stack

     roth-=0.008f;


     //trainmaking

         glBegin(GL_QUADS); //road
    glColor3f(0.0f, 1.0f, 0.0f);//Green
    glVertex2f( -1, -0.6 );
    glColor3f(0.0f, 1.0f, 0.0f);//Green
    glVertex2f( 1, -0.6 );
    glColor3f(0.0f, 1.0f, 0.0f);//Green
    glVertex2f( 1, -2);
    glColor3f(0.0f, 1.0f, 0.0f);//Green
    glVertex2f( -1, -2 );
    glEnd();

    //raillines

    glBegin(GL_LINES);//raillines1-1
	glColor3f(0, 0, 0.);
	glVertex2f(-1, -0.91);
	glVertex2f(1, -0.91);
	glEnd();

	glBegin(GL_LINES);//raillines1-2
	glColor3f(0, 0, 0.);
	glVertex2f(-1, -0.90);
	glVertex2f(1, -0.90);
	glEnd();


	 glBegin(GL_LINES);//raillines1-1
	glColor3f(0, 0, 0.);
	glVertex2f(-1, -0.75);
	glVertex2f(1, -0.75);
	glEnd();

	glBegin(GL_LINES);//raillines1-2
	glColor3f(0, 0, 0.);
	glVertex2f(-1, -0.74);
	glVertex2f(1, -0.74);
	glEnd();

	//railbracks

	glBegin(GL_LINES);//railbracks1
	glColor3f(0, 0, 0.);
	glVertex2f(-1.04, -0.91);
	glVertex2f(-0.97, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks2
	glColor3f(0, 0, 0.);
	glVertex2f(-0.97, -0.91);
	glVertex2f(-0.9, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks3
	glColor3f(0, 0, 0.);
	glVertex2f(-0.87, -0.91);
	glVertex2f(-0.8, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks4
	glColor3f(0, 0, 0.);
	glVertex2f(-0.77, -0.91);
	glVertex2f(-0.7, -0.74);
	glEnd();


	glBegin(GL_LINES);//railbracks5
	glColor3f(0, 0, 0.);
	glVertex2f(-0.67, -0.91);
	glVertex2f(-0.6, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks6
	glColor3f(0, 0, 0.);
	glVertex2f(-0.57, -0.91);
	glVertex2f(-0.5, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks7
	glColor3f(0, 0, 0.);
	glVertex2f(-0.47, -0.91);
	glVertex2f(-0.4, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks8
	glColor3f(0, 0, 0.);
	glVertex2f(-0.37, -0.91);
	glVertex2f(-0.3, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks9
	glColor3f(0, 0, 0.);
	glVertex2f(-0.27, -0.91);
	glVertex2f(-0.2, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks10
	glColor3f(0, 0, 0.);
	glVertex2f(-0.17, -0.91);
	glVertex2f(-0.1, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks11
	glColor3f(0, 0, 0.);
	glVertex2f(-0.07, -0.91);
	glVertex2f(0.0, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks12
	glColor3f(0, 0, 0.);
	glVertex2f(0.04, -0.91);
	glVertex2f(0.1, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks13
	glColor3f(0, 0, 0.);
	glVertex2f(0.14, -0.91);
	glVertex2f(0.2, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks14
	glColor3f(0, 0, 0.);
	glVertex2f(0.24, -0.91);
	glVertex2f(0.3, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks15
	glColor3f(0, 0, 0.);
	glVertex2f(0.34, -0.91);
	glVertex2f(0.4, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks16
	glColor3f(0, 0, 0.);
	glVertex2f(0.44, -0.91);
	glVertex2f(0.5, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks17
	glColor3f(0, 0, 0.);
	glVertex2f(0.54, -0.91);
	glVertex2f(0.6, -0.74);
	glEnd();


	glBegin(GL_LINES);//railbracks18
	glColor3f(0, 0, 0.);
	glVertex2f(0.64, -0.91);
	glVertex2f(0.7, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks19
	glColor3f(0, 0, 0.);
	glVertex2f(0.74, -0.91);
	glVertex2f(0.8, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks20
	glColor3f(0, 0, 0.);
	glVertex2f(0.84, -0.91);
	glVertex2f(0.9, -0.74);
	glEnd();

	glBegin(GL_LINES);//railbracks21
	glColor3f(0, 0, 0.);
	glVertex2f(0.94, -0.91);
	glVertex2f(1, -0.74);
	glEnd();

	//railrim

	 glPushMatrix();
    glTranslatef(positioncar,0,0);

	 //1 railrim



    GLfloat railrim1=-0.85f; GLfloat railrim11=-0.87f; GLfloat railrim111 =.04f;








    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                railrim1 + (railrim111 * cos(i *  twicePi / lineAmount)),
                railrim11 + (railrim111* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

//2 rim


    GLfloat railrim2=-0.7f; GLfloat railrim22=-0.87f;




    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                railrim2 + (railrim111 * cos(i *  twicePi / lineAmount)),
                railrim22 + (railrim111* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();


//3rd rim


    GLfloat railrim3=-0.50f; GLfloat railrim33=-0.87f;




    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                railrim3 + (railrim111 * cos(i *  twicePi / lineAmount)),
                railrim33 + (railrim111* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

    //4th rim


    GLfloat railrim4=-0.35f; GLfloat railrim44=-0.87f;




    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                railrim4 + (railrim111 * cos(i *  twicePi / lineAmount)),
                railrim44 + (railrim111* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

     //5th rim


    GLfloat railrim5=-0.18f; GLfloat railrim55=-0.87f;




    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                railrim5 + (railrim111 * cos(i *  twicePi / lineAmount)),
                railrim55 + (railrim111* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

    //6th rim


    GLfloat railrim6=-0.02f; GLfloat railrim66=-0.87f;




    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                railrim6 + (railrim111 * cos(i *  twicePi / lineAmount)),
                railrim66 + (railrim111* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

    //7th rim


    GLfloat railrim7=0.14f; GLfloat railrim77=-0.87f;




    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                railrim7 + (railrim111 * cos(i *  twicePi / lineAmount)),
                railrim77 + (railrim111* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

    //8th rim


    GLfloat railrim8=0.30f; GLfloat railrim88=-0.87f;




    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                railrim8 + (railrim111 * cos(i *  twicePi / lineAmount)),
                railrim88 + (railrim111* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

    //9th rim


    GLfloat railrim9=0.48f; GLfloat railrim99=-0.87f;




    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                railrim9 + (railrim111 * cos(i *  twicePi / lineAmount)),
                railrim99 + (railrim111* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();

    //10th rim


    GLfloat railrim101=0.62f; GLfloat railrim1011=-0.87f;




    glBegin(GL_TRIANGLE_FAN);
    glColor3f(0.0f, 0.0f, 0.0f);//Black
        for(i = 0; i <= lineAmount;i++) {
            glVertex2f(
                railrim101 + (railrim111 * cos(i *  twicePi / lineAmount)),
                railrim1011 + (railrim111* sin(i * twicePi / lineAmount))
            );
        }
    glEnd();



    //trainhimself

    glBegin(GL_QUADS); //train1stbogy1
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( -0.91, -0.86 );
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( -0.61, -0.86 );
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( -0.61, -0.55 );
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( -0.91, -0.55 );
    glEnd();

    glBegin(GL_QUADS); //train1stbogy2
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( -0.58, -0.86 );
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( -0.28, -0.86 );
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( -0.28, -0.55 );
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( -0.58, -0.55 );
    glEnd();

     glBegin(GL_QUADS); //train1stbogy3
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( -0.25, -0.86 );
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( 0.05, -0.86 );
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( 0.05, -0.55 );
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( -0.25, -0.55 );
    glEnd();

    glBegin(GL_QUADS); //train1stbogy4
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( 0.08, -0.86 );
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( 0.38, -0.86 );
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( 0.38, -0.55 );
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( 0.08, -0.55 );
    glEnd();

    glBegin(GL_QUADS); //train1stbogy5
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( 0.41, -0.86 );
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( 0.58, -0.86 );
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( 0.58, -0.55 );
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( 0.41, -0.55 );
    glEnd();

    glBegin(GL_TRIANGLES); //trainbogyhead
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( 0.58, -0.86 );
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( 0.7, -0.86 );
    glColor3f(0.5f, 0.5f, 0.5f);
    glVertex2f( 0.55, -0.6 );
    glEnd();

    //trainwindowndoor

    glBegin(GL_QUADS); //train1stbogy1 door
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( -0.88, -0.82 );
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( -0.78, -0.82 );
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( -0.78, -0.58 );
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( -0.88, -0.58 );
    glEnd();

    glBegin(GL_QUADS); //train1stbogy1 window
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( -0.74, -0.72 );
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( -0.64, -0.72 );
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( -0.64, -0.56 );
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( -0.74, -0.56 );
    glEnd();

    glBegin(GL_QUADS); //train1stbogy2 window
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( -0.55, -0.72 );
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( -0.3, -0.72 );
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( -0.3, -0.56 );
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( -0.55, -0.56 );
    glEnd();


    glBegin(GL_QUADS); //train1stbogy3 door
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( -0.11, -0.82 );
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( -0.21, -0.82 );
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( -0.21, -0.58 );
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( -0.11, -0.58 );
    glEnd();

    glBegin(GL_QUADS); //train1stbogy3 window
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( -0.07, -0.72 );
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( 0.03, -0.72 );
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( 0.03, -0.56 );
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( -0.07, -0.56 );
    glEnd();

    glBegin(GL_QUADS); //train1stbogy4 window
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( 0.1, -0.72 );
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( 0.36, -0.72);
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( 0.36, -0.56 );
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( 0.1, -0.56 );
    glEnd();

    glBegin(GL_QUADS); //train1stbogy5 door
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( 0.53, -0.82 );
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( 0.43, -0.82 );
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( 0.43, -0.58 );
    glColor3f(0.0f, 0.0f, 0.0f);
    glVertex2f( 0.53, -0.58 );
    glEnd();


    glPopMatrix();



    glFlush();  // Render now


}

////////////////////////////////////////////////////////////////////////////////////////////

void handleKeypress(unsigned char key, int x, int y) {

	switch (key) {

    case 'm':
     glutDisplayFunc(morning);
     glutPostRedisplay();

    break;
    case 'd':
    glutDisplayFunc(day);
    glutPostRedisplay();

    break;

    case 'n':
    glutDisplayFunc(night);
    glutPostRedisplay();

    break;

    case 't':
    glutDisplayFunc(traffic);
    glutPostRedisplay();

    break;



glutPostRedisplay();


	}


}



/* Main function: GLUT runs as a console application starting at main()  */
int main(int argc, char** argv) {

	glutInit(&argc, argv);                 // Initialize GLUT
	glutCreateWindow("Model View"); // Create a window with the given title
	glutInitWindowSize(320, 320);   // Set the window's initial width & height
	glutDisplayFunc(morning); // Register display callback handler for window re-paint
	glutIdleFunc(Idle);//glutIdleFunc sets the global idle callback to be func so a
    glutTimerFunc(100, updatecar, 0);
    glutTimerFunc(100, updatecloud, 0);
    glutKeyboardFunc(handleKeypress);
	glutMainLoop();           // Enter the event-processing loop
	return 0;
}

